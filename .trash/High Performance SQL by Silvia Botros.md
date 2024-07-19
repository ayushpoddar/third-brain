---
annotation-target: https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1
---


>%%
>```annotation-json
>{"created":"2024-07-08T04:22:44.147Z","updated":"2024-07-08T04:22:44.147Z","document":{"title":"High Performance MySQL","link":[{"href":"urn:x-pdf:1401f3fc173d4f5b6cc8342d4af50fdd"},{"href":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1"}],"documentFingerprint":"1401f3fc173d4f5b6cc8342d4af50fdd"},"uri":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","target":[{"source":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","selector":[{"type":"TextPositionSelector","start":434991,"end":435575},{"type":"TextQuoteSelector","exact":"You can often save space and get good performance by indexing the first few charac‐ters  instead  of  the  whole  value.  This  makes  your  indexes  use  less  space,  but  it  alsomakes  them  less  selective.  Index  selectivity  is  the  ratio  of  the  number  of  distinctindexed  values  (the  cardinality)  to  the  total  number  of  rows  in  the  table  (#T),  and  itranges  from  1/#T  to  1.  A  highly  selective  index  is  good  because  it  lets  MySQL  filterout more rows when it looks for matches. A unique index has a selectivity of 1, whichis as good as it gets","prefix":"ix Indexes and Index Selectivity","suffix":".A prefix of the column is often"}]}]}
>```
>%%
>*%%PREFIX%%ix Indexes and Index Selectivity%%HIGHLIGHT%% ==You can often save space and get good performance by indexing the first few charac‐ters  instead  of  the  whole  value.  This  makes  your  indexes  use  less  space,  but  it  alsomakes  them  less  selective.  Index  selectivity  is  the  ratio  of  the  number  of  distinctindexed  values  (the  cardinality)  to  the  total  number  of  rows  in  the  table  (#T),  and  itranges  from  1/#T  to  1.  A  highly  selective  index  is  good  because  it  lets  MySQL  filterout more rows when it looks for matches. A unique index has a selectivity of 1, whichis as good as it gets== %%POSTFIX%%.A prefix of the column is often*
>%%LINK%%[[#^36ju3dx66vy|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^36ju3dx66vy



>%%
>```annotation-json
>{"created":"2024-07-08T04:26:43.443Z","updated":"2024-07-08T04:26:43.443Z","document":{"title":"High Performance MySQL","link":[{"href":"urn:x-pdf:1401f3fc173d4f5b6cc8342d4af50fdd"},{"href":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1"}],"documentFingerprint":"1401f3fc173d4f5b6cc8342d4af50fdd"},"uri":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","target":[{"source":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","selector":[{"type":"TextPositionSelector","start":435804,"end":436138},{"type":"TextQuoteSelector","exact":"The  trick  is  to  choose  a  prefix  that’s  long  enough  to  give  good  selectivity  but  shortenough to save space. The prefix should be long enough to make the index nearly asuseful as it would be if you’d indexed the whole column. In other words, you’d like theprefix’s cardinality to be close to the full column’s cardinality","prefix":"lows indexing their full length.","suffix":".To determine a good prefix leng"}]}]}
>```
>%%
>*%%PREFIX%%lows indexing their full length.%%HIGHLIGHT%% ==The  trick  is  to  choose  a  prefix  that’s  long  enough  to  give  good  selectivity  but  shortenough to save space. The prefix should be long enough to make the index nearly asuseful as it would be if you’d indexed the whole column. In other words, you’d like theprefix’s cardinality to be close to the full column’s cardinality== %%POSTFIX%%.To determine a good prefix leng*
>%%LINK%%[[#^sb3v61qskl8|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^sb3v61qskl8


>%%
>```annotation-json
>{"created":"2024-07-08T04:27:46.510Z","updated":"2024-07-08T04:27:46.510Z","document":{"title":"High Performance MySQL","link":[{"href":"urn:x-pdf:1401f3fc173d4f5b6cc8342d4af50fdd"},{"href":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1"}],"documentFingerprint":"1401f3fc173d4f5b6cc8342d4af50fdd"},"uri":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","target":[{"source":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","selector":[{"type":"TextPositionSelector","start":438720,"end":438925},{"type":"TextQuoteSelector","exact":"Another way to calculate a good prefix length is by computing the full column’s selec‐tivity and trying to make the prefix’s selectivity close to that value. Here’s how to findthe full column’s selectivity","prefix":"47  | Shimoga |+-----+---------+","suffix":":mysql> SELECT COUNT(DISTINCT ci"}]}]}
>```
>%%
>*%%PREFIX%%47  | Shimoga |+-----+---------+%%HIGHLIGHT%% ==Another way to calculate a good prefix length is by computing the full column’s selec‐tivity and trying to make the prefix’s selectivity close to that value. Here’s how to findthe full column’s selectivity== %%POSTFIX%%:mysql> SELECT COUNT(DISTINCT ci*
>%%LINK%%[[#^m32crwqvdw|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^m32crwqvdw


>%%
>```annotation-json
>{"created":"2024-07-08T04:29:06.609Z","text":"![](https://www.dropbox.com/scl/fi/1yj48fw9vlrglmmxlbo3s/SCR-20240708-jeos.png?rlkey=k5b2q1pvmlcsx0vegys73ooy3&dl=1)","updated":"2024-07-08T04:29:06.609Z","document":{"title":"High Performance MySQL","link":[{"href":"urn:x-pdf:1401f3fc173d4f5b6cc8342d4af50fdd"},{"href":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1"}],"documentFingerprint":"1401f3fc173d4f5b6cc8342d4af50fdd"},"uri":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","target":[{"source":"https://www.dropbox.com/scl/fi/bhyuocyyt81w2styybodv/Silvia-Botros-High-Performance-MySQL-Proven-Strategies-for-Operating-at-Scale-2021-do-not-rename.pdf?rlkey=mbjkk5vc0qflrddxk3svd48pc&dl=1","selector":[{"type":"TextPositionSelector","start":438933,"end":438992},{"type":"TextQuoteSelector","exact":"SELECT COUNT(DISTINCT city)/COUNT(*) FROM sakila.city_demo;","prefix":"ull column’s selectivity:mysql> ","suffix":"+-------------------------------"}]}]}
>```
>%%
>*%%PREFIX%%ull column’s selectivity:mysql>%%HIGHLIGHT%% ==SELECT COUNT(DISTINCT city)/COUNT(*) FROM sakila.city_demo;== %%POSTFIX%%+-------------------------------*
>%%LINK%%[[#^1iwmjvpvyv2|show annotation]]
>%%COMMENT%%
>![](https://www.dropbox.com/scl/fi/1yj48fw9vlrglmmxlbo3s/SCR-20240708-jeos.png?rlkey=k5b2q1pvmlcsx0vegys73ooy3&dl=1)
>%%TAGS%%
>
^1iwmjvpvyv2
