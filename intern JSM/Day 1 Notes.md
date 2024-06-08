### Working with Node.js streams - 

when we want to work with large amounts of data with big files, reading and writing and performing operations on those files can largely increase the memory consumption of the express server we have created.

To solve this issue we can use streams, which will make the data availabale to user as we are getting it. , a single chunk of data from the stream is brought into the memory, at a time.

Read the file chunk by chunk and keep sending it to the browser

### Cluster Modules in Node: 

Working with multiple cores so that we can handle api's in a parallel manner. Used to make use of multiple threads


store inventory -> date, opening Quant, Closing quant, purchased, issued, wasted