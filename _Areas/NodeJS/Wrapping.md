- Module's code is wrapped into a special function
- NodeJS takes the code of the module and puts it inside the immediately invoked function expression (IIFE), which looks like this: ![[Pasted image 20221020170010.png]]
- So, node does not directly execute the code of a file, but the above wrapper function
- The function also has `require`, `module`, etc. as arguments. This is why we have access to these functions in every file
- This helps to give each module its own private scope