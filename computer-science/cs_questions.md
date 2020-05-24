## NETWORKING

1. Read the concept of TCP in [this wiki page](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) and try to understand all the concepts of it (deeply):
    - How TCP open a connection? what does it need to open a connection?
        + Why there are 3 way handsharks but not 2 way? 
        + What is syn, ack mean?
        + Why they have to send 2 "random" sequence number? The purpose of this sequence number?
        + What if the 3rd handshark fail? How server can detect it and what does it do in this case?
    - How TCP handle the connection?
        + What happens if some bits are wrong due to connection errors? How to detect them and fix them?
        + How the timeout is handle? what if the timeout is exprise?
        + What will happen if some "packet" is missing on the way?
        + How to detect the appropriate number of packet to send (speed of sending packet)?
    - How TCP close the connection?
        + What if the internet is drop in the middle of connection? Or in case one peer is crash?
    - How long you can keep a TCP connection alive?

2. What are the differents between TCP and UDP? And in which case we use which?

3. How ping command works? What is TTL?? How does TTL will be changed?? 

4. How HTTP works?
    - Why people said that HTTP is stateless? The reason we they make it stateless?
    - Can we make a persistent HTTP connection? pros and cons of this way?
    - Why http require cookie each time we send the request?
    - Can some one use your cookie and log in your facebook account? How to migrate this?
    - What is HTTP session? How authentication works in HTTP? What is JWT?
    - Which type of "data" HTTP can help us to get or push? (binary file? image? text file? video file? music file?)
    - REST/RESTful?
    - AJAX technique? 
    - How HTTPs work?
    - Learn about some useful headers.

5. When you type "google.com" into your broswer, that will happen when you type enter till everything is display on your screen?
    - DNS lookup (in case you already access google.com before and also in case you do not know the IP of google.com)
        + Which protocol DNS use and why?
        + The other of place to look up DNS.
    - TCP or UDP will be use in this case? why?
    - How to know "google.com" require http or https? how brower can know and redirect from http to https?
    - After you get the `HTML content` for "google.com" how to get the `*.js` and `image` files?
    - When getting `*.js` or `image` files do why use another `TCP connection` or use the same one as in the get `HTML content`? How DNS look up work in this case?
    - After your broswer display "google.com" fully, are there any connection open?
    - Caching can apply to which steps? How caching applied?

6. What is connection pool? It's advantages and disadvantages? How to implement connection pool in your programing language?

7. What is socket?
    - Why do we need socket? Why socket is a "file" in linux?
    - What is `src port` when you create a connection to a "server"?
    - What one server can handle multiple connections to a same port? [Good answers here but read all answers](https://stackoverflow.com/questions/3329641/how-do-multiple-clients-connect-simultaneously-to-one-port-say-80-on-a-server)
    - What is the maximum number of connections a server can handle? (if it has unlimited resource) (in case of same client and in case of multiple clients)
    - When you open multiple tabs on your chrome, how OS know which packet (both sending and recieving) corespond to which tab? (how about in case you open many tabs to the same page "for eg: google.com")
    - What is the maximum numbers of connection your machine can connection to "google.com" (if you have unlimited resource)
    - Can two process listen to the same port on your machine? Why? How?
    - What is `buffer`? why we always need buffer when work with "file"?
    - What is `unix socket`? When to use it?

8. What is `TCP proxy`? `reverse proxy`? and `VPN`?
    - How your router at your home works?
        + Inside LAN network, it use IP or MAC address? Why?
        + How does it know which packet come from (or arrive at) which machine?
        + What is the different between Hub and Swtich inside LAN?
        + How src IP/PORT and dst IP/PORT change on the way to the server?
    - How `load-balancer` works? (this one is a tough question) // hint: it opposite to how to router work. 
        + When we send a packet to a `load-balancer` how does it forward to the desired server? (Does it keep any data on its memory?)
        + When the server want to send data back to client, does the connection need to go through `load-balancer`? 
        + What is different between `reverse proxy` and `load-balancer`?
        + Can `load-balancer` be a bottle neck? (Because it is the end-point of too many requests) (bottle neck about RAM or CPU or Network?)
        + Try to understand everything in [this page](https://softwareengineering.stackexchange.com/questions/312956/what-does-a-load-balancer-return) (all the answers)

## OPERATING SYSTEM

1. What is `process`, `thread`? What are differents between them?
    - What data `process`, `thread` need to live? Why they said that `Thread is a lightweight process`?
    - How CPU switch (context switch) between `processes`/`theads`? How data is ensure safety? (in case single CPU core and multiple CPU core)
    - What is `multi-process` and `multi-thread`? When we should you which?
        + Process have how many state? How does it change between each state?
        + Scheduling algorithm.
        + What will happen if a process is `waiting`? Or a thread is `sleeping`?
        + How CPU detect that a thread is `sleeping`? Or detech when it want to run?
    - What is `thread-pool`? How to use it? Describe how to create a `thread-pool` in your programming language
    - Can 2 different processes access or change data of each other `address space`? (this question may make you confuse with your knowledge about `virtual memory`)
        + Can 2 processes use the same library (for eg: libc is required to every process)? How?
        + How does `debugger` work? How it can attach to a running process and change data of that process? (so cool, right?)
    - How 2 process can comunicate with each other? (There are lot of way but focus on the OS's way)
    - What is `child-process`? How to create a `child-process`?
        + What data a `child-process` have when we create it?
        + Can it read/write data on it's `parent process`?
        + What is `copy on write (COW)`? **(this concept is important to understand OS)** // if you love computer security like me you can read more about `Dirty COW`, it's fabulous
        + What will happend when `child-process` change a variable of `parent process`?
        + If `file descriptor` also be `inherited` by `child process`. What if 2 process can handle a same `file descriptor` or even a same `socket`? can refer [here](https://www.cs.ait.ac.th/~on/O/oreilly/perl/cookbook/ch17_10.htm)

2. `Concurrency` vs `Parallels`? (in case single CPU core and multiple CPU core)
    - What is `critical zone`? 
    - What is `race condition` and how to handle this case?
    - What is locking mechanism? `mutex`? `semaphore`? `spin lock`? `read lock` vs `write lock`?
    - What is `dead lock` and how to avoid `dead lock`?

3. How does memory is managed in OS?
    - What is `virtual memory`? Why do we need it? How does it work?
        + How large `virtualy memory` is?
        + What is `paging`?
        + Can 2 processes map to the same `physical address`? How and in which case?
    - What is `heap space` and `stack space`?
    - What will happen with memory when you open an application?
    - What will happen you call another function (with parameters) or return from a function? 
        + What will happen with stack? (why we do not use heap here?)? 
        + What will happen with registor?
    - What cause stack-over-flow?
    - What is dynamic allocating? How does it work? 
        + How does deallocation work?
        + What happen when your computer is full of memory?
    - Why you do not need to "deallocate" local variable?
    - How does `Garbage Collection` work? When it will be trigger?
    - What is a pointer? What different between `pass by value` and `pass by reference`?
    - Where `global variable` will be saved?

4. Why in linux `everything is "file"`?
    - How does mouse/keyboard/monitor..... communicate with your computer?
    - What is `file descriptor`?
    - What is `buffer`? Why do we need `buffer`?
    - What will happen if 2 processes read/write to a same file?

5. What is `system call (syscal)`?
    - How to do a `syscal`?
    - What happen with CPU when we execute a `syscal`?
    - What is `user space` and `kernel space`?

6. Caching:
    - What is in memory cache? (memcached/redis)
    - LRU? implement LRU in your program language! (How about multi thread?)
    - How to migrate `Cache stampede`?
    - Quicksort(O(n^2) in worst case) vs Merge sort (O(nlogn) in worst case). Which is faster? Why? How they use these 2 sorting algorithm in real life?

- Good resources:
    * [Overview of OS syntax, try do dive deeper to each concept](https://medium.com/cracking-the-data-science-interview/the-10-operating-system-concepts-software-developers-need-to-remember-480d0734d710)


## DATABASE

1. Compare `Relational DB (SQL)` vs `NoSQL`. It's also really nice to know about `newSQL` (a kind of auto sharding DB which support `SQL stuff` but scale like `NoSQL`) 
    - How these 2 things can scale up?
    - How Transaction is handled? 
    - `ACID` of `SQL` and `BASE` of `NoSQL`? Why `NoSQL` is `eventual consistency`?
    - `CAP` theorem in this case. [This is a so nice graph](http://blog.nahurst.com/visual-guide-to-nosql-systems)

2. What is `parameterized statement` (in Java it's `prepared statement`)? How does it work **internally**?
    - What is `SQL injection`? how to avoid it?
    - How many "request" you have to send to `Database` in a single `prepared statement` query? // one for compile and one for execute
    - Can you reuse the `compiled` query multiple time? (does it help to speed up your application?)

3. How `indexing` works internally?
    - What algorithm and data structure `indexing` used? And why?
    - How `composite indexing` works?
    - How to know your query is using index?
    - How index work in this case: `WHERE age = 5` and `Where age > 5`? The complexity to go to next record?
    - Indexing with char?

4. Complexity of SQL query? How to measure it? How SQL optimize a query?
    - Compare `WHERE id = 'a' AND id = 'b' AND id = 'c'` vs `WHERE id in (a, b, c)`?
    - Complexity of this query `SELECT * FROM abc ORDER BY name LIMIT 10 OFFSET 1000000` // SELECT 10 record from offset 10^6 after sort by name (which is a char)? How to optimize it?
    - What is the complexity of `COUNT(*)` query?
    - How to write query to avoid full table scan?
    - Complexity of `JOIN`, `INNER JOIN`, `OUTTER JOIN`?

5. What is Database Replicating? When we need it?
    - What is `bin log`? How `Master DB` sync with `Slave DB`?
    - Can a `Slave DB` be a slave of another `Slave DB` (we do not need to sync from `Master DB` directly)?

6. What is Database Sharding? When we need it?
    - Which rule we can apply to DB Sharding?
    - How to ensure `primary key` is global unique when sharding?
    - How we can shard a table to multiple table (same server) and multiple DB (multiple server)?
    - How query can work when we sharding? for example query but the data is in different tables/dbs?

7. What is database transaction?
    - How `rollback` works internally?
    - `ACID`? What is `dirty read`?
    - How transaction work when there are many concurrent request?
    - How to avode `race condition` in DB? `Read/Write` lock?
    - `Distributed transaction`? How to make a transaction when a query need to access multiple DB?


## SECURITY

1. Hash vs Encrypt vs Encode
    - Are there any way we can crack `Hash`
    - symmetric vs asyncmetric encryption? AES vs RSA?
    - Fast Hash vs Slow Hash?
    - When we use Encode??
    - What is the perfect hash function?
    - What is load factor of hashing?

2. SSL/TLS
    - How to verify a certificate? How many kind of certificate are there?
    - What is CA? how to verify certificate of a CA?
    - What is `public`/`private` key? what is symetric `key`
    - What is digital signature? What is `HMAC`?

3. How to store credential information effiency? (user password, config key, database credential, user information, secret key,.... )

4. Decribe a way to defense DDOS? (actually there are many kind of DDOS not just network OS, so this question is pretty complicated)
