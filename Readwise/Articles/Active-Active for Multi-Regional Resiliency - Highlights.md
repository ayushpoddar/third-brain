![rw-book-cover](https://miro.medium.com/max/734/0*zjuCxXJlkL9SrlS1.)

## Metadata
- Author: [[Netflix Technology Blog]]
- Full Title: Active-Active for Multi-Regional Resiliency
- URL: https://netflixtechblog.com/active-active-for-multi-regional-resiliency-c47719f6685b

## Highlights
- Once scale starts to grow, even with slow velocity, the chance of hardware failure will increase. Conversely, even at small scale, if velocity is fast enough, chance of software failure will increase. Ultimately, if you’re running at scale and still pursuing high velocity — things will break all the time. ([View Highlight](https://read.readwise.io/read/01gyee273jz4s2356mmzxgmhnn))
- We had to enhance Zuul beyond it’s original set of capabilities in order to enable Active-Active use cases and operational needs. The enhancements were in several areas:
  • Ability to identify and handle mis-routed requests. User request is defined as mis-routed if it does not conform to our geo directional records. This ensures a single user device session does not span multiple regions. We also have controls for whether to use “isthmus” mode to send mis-routed requests to the correct AWS Region, or to return a redirect response that will direct clients to the correct Region. ([View Highlight](https://read.readwise.io/read/01gyejr5a50kq2atzz9bqp33mm))
    - Note: The given content describes a system that can detect and manage mis-routed user requests, which are requests that do not align with geographical data on the user's location. This is done to prevent a single user device session from spanning across multiple regions.
      Mis-routed requests occur when a user's request is sent to the wrong server or region, which can cause latency or other performance issues. In this context, the system uses "geo directional records" to determine the correct server or region to handle the user's request.
      To address mis-routed requests, the system offers two options:
      1. Isthmus mode: This mode automatically forwards the mis-routed request to the correct Amazon Web Services (AWS) Region where the appropriate server is located. This ensures that the user's request is still processed, even if it was initially sent to the wrong region.
      2. Redirect response: Instead of directly forwarding the request to the correct region, the system returns a redirect response to the client, instructing it to send the request to the appropriate region. This requires the client to resend the request to the correct server or region.
      By having the ability to identify and handle mis-routed requests, the system can improve user experience and maintain optimal performance by ensuring that user requests are processed by the appropriate servers in the correct regions.
      Geo-directional records, also known as geo-based or geo-location records, are a type of DNS (Domain Name System) record that allows the distribution of network traffic based on the geographical location of the user making the request and the server handling the request. These records help in optimizing the routing of user requests to the nearest or most appropriate server, improving the user experience by reducing latency and enhancing overall performance.
      When a user makes a request to access a website or service, the DNS system uses the geo-directional records to determine the closest or most suitable server to handle the request, based on the user's geographical location. This ensures that users are directed to the server that can provide the best performance and response time, minimizing the distance that data has to travel.
      Geo-directional records are an important tool for managing global network traffic and providing a better experience to users by ensuring that their requests are handled by the most appropriate server in the most efficient way possible.
- • Ability to declare a region in a “failover” mode — this means it will no longer attempt to route any mis-routed requests to another region, and instead will handle them locally
  • Ability to define a maximum traffic level at any point in time, so that any additional requests will be automatically shed (response == error), in order to protect downstream services against a thundering herd of requests. Such ability is absolutely necessary in order to protect services that are still scaling up in order to meet growing demands, or when regional caches are cold, so that the underlying persistence layer does not get overloaded with requests. ([View Highlight](https://read.readwise.io/read/01gyejx3qdy44y9evhpyvsry8e))
- One of the more interesting challenges in implementing Active-Active, was the replication of users’ data/state. Netflix has embraced Apache Cassandra as our scalable and resilient NoSQL persistence solution. One of inherent capabilities of Apache Cassandra is the product’s multi-directional and multi-datacenter (multi-region) asynchronous replication. For this reason all data read and written to fulfil users’ requests is stored in Apache Cassandra. ([View Highlight](https://read.readwise.io/read/01gyejy1gsrz7n1a8rr5ak3jdh))
- Since many of our applications that serve user requests need to do so in a timely manner, we need to guarantee that data tier reads are fast — generally in a single-millisecond range. In some cases, we also front our Cassandra clusters with a Memcached layer, in other cases we have ephemeral calculated data that only exists in Memcached. Managing memcached in a multi-regional Active-Active setup leads to a challenge of keeping the caches consistent with the source of truth. Rather than re-implementing multi-master replication for Memcached, we added remote cache invalidation capability to our [EvCache client](https://medium.com/@Netflix_Techblog/announcing-evcache-distributed-in-memory-datastore-for-cloud-c26a698c27f7) — a memcached client library that we open sourced earlier in 2013. Whenever there is a write in one region, EvCache client will send a message to another region (via SQS) to invalidate the corresponding entry. Thus a subsequent read in another region will recalculate or fall through to Cassandra and update the local cache accordingly. ([View Highlight](https://read.readwise.io/read/01gyekff9tr6k94wr3fxvfraqs))
    - Note: A multi-master replication system for Memcached refers to a setup where multiple Memcached servers (masters) work in parallel and replicate data between them, allowing any of the master servers to accept updates and synchronize their data. 
      Memcached is an in-memory key-value store typically used for caching purposes in web applications to reduce the load on databases and improve performance. By default, Memcached does not have built-in replication or redundancy features.
      In a multi-master replication system:
      1. Each master server operates independently and can accept both read and write requests.
      2. When data is updated on one master server, it is automatically synchronized with the other master servers in the system.
      3. In case a master server fails or becomes unavailable, the remaining master servers can continue to operate and serve requests without any disruption.
      This setup provides increased fault tolerance, redundancy, and load distribution across the system. It ensures that the data is still available even if one or more master servers fail, and it allows the workload to be balanced across multiple servers, improving overall system performance.
      It's worth noting that Memcached itself does not provide built-in multi-master replication functionality. However, there are third-party solutions and approaches that can be used to implement multi-master replication for Memcached, such as using replication tools like repcached or integrating with other distributed caching systems like Redis.