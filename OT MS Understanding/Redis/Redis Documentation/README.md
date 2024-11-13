# REDIS DOCUMENTATION

| **Author** | **Created on** | **Version** | **Last updated by** | **Last edited on** |
|------------|----------------|-------------|----------------------|---------------------|
| Anugra .W. Lepcha       | 12-11-24      | version 1   | Anugra .W. Lepcha                | 13-11-24           |


# Redis: Remote Dictionary Server

**Redis**, which stands for **Remote Dictionary Server**, was created by **Salvatore Sanfilippo** in 2009. Sanfilippo originally developed Redis while working on an Italian startup called **Loggly**, where he needed a solution to manage large volumes of log data in real time. Traditional databases at the time struggled to handle this requirement efficiently, so he created Redis to provide extremely fast data retrieval by keeping data in memory rather than on disk.

Redis was initially designed to handle simple key-value pairs but soon evolved to support more complex data structures such as lists, sets, and hashes. These added features made Redis a versatile tool for caching, message brokering, and even primary data storage.

The software's open-source nature, simplicity, and high performance made it a preferred choice for caching, real-time analytics, and session management in web applications, leading to its significant adoption and continued evolution in the tech world.

### What is Redis?

**Redis** is an open-source, in-memory data store that is commonly used as a **cache**, **message broker**, and even as a **database**. It’s designed for situations where speed is crucial, allowing applications to quickly read and write data to memory rather than relying on disk storage, which is slower. This makes Redis ideal for applications that require fast access to data, like real-time analytics, session management, and caching frequently accessed information.

Redis supports a wide variety of data structures, such as strings, lists, sets, hashes, and sorted sets, giving it a lot of flexibility. One of Redis’s key strengths is its ability to handle **atomic operations**, which ensures that data modifications happen as a single, indivisible operation. This is particularly useful for scenarios where accurate and fast data access is essential, such as caching, where quick data retrieval significantly improves user experience and system performance.

### Why Use an In-Memory Database?

Redis is an **in-memory database**, meaning it stores data entirely in **main memory (RAM)** rather than on disk. This is a key reason why Redis performs so well: accessing data in memory is significantly faster than accessing data on a disk. 

In-memory databases are optimized for speed and are commonly used in applications that demand quick access to large volumes of data. Here are some example use cases:

- **Real-Time Analytics**: In-memory databases can process and retrieve data in real time, making them ideal for applications that need to analyze data instantly, such as financial systems or IoT applications.
- **Online Gaming**: Many gaming applications require real-time data access for player statistics, leaderboards, and matchmaking, which are well-suited to an in-memory store like Redis.
- **E-commerce**: E-commerce platforms often use Redis for managing shopping cart sessions, caching product details, and handling flash sales where fast access to data is essential.
- **Social Media**: In-memory databases can handle rapid data retrieval for activities like managing user feeds and notifications.

### What is Caching?

**Caching** is a technique for storing frequently accessed data temporarily in a "cache" for quick retrieval. **Redis** is an **in-memory database** that stores data in **RAM** instead of on disk, allowing fast data processing. Redis is ideal for caching because of its high-speed data retrieval, which helps reduce unnecessary requests to the main database.

![alt text](image-7.png)

## How Does Caching in Redis Work?

Redis stores frequently used data in memory for fast access. When a request is made, Redis first checks if the data is already in memory. If it is, it returns the data quickly. If not, Redis fetches it from the database and stores it in memory for future use. Here’s how it works:

1. **Cache Miss**: Redis checks if the data is in memory. If not, it gets it from the database.
2. **Cache Hit**: If the data is in memory, Redis returns it instantly.
3. **Cache Update**: Redis stores the new data in memory for faster access next time.
4. **Cache Invalidation**: When the database data changes, Redis updates or removes the cached data to keep everything in sync.

![alt text](image-6.png)

### Redis Persistence

Redis persistence is a feature of the Redis database that allows data to be saved to disk and restored in the event of a crash or shutdown. By default, Redis stores data in memory, which means that it is lost when the Redis server is shut down or restarted. Redis persistence enables data to be saved to disk and restored when the Redis server starts up again, ensuring that data is not lost in the event of a crash or shutdown.
Redis persistence can be configured in several ways, depending on the needs of the application. The simplest form of persistence is **snapshotting**, which involves periodically saving the entire Redis dataset to disk. This approach is fast and efficient, but it can result in data loss if the Redis server crashes between snapshots.

![alt text](image-9.png)

Another form of persistence is **Append-Only File (AOF)** persistence, which involves saving each write operation to a log file on disk. This approach provides better durability than snapshotting, as it allows the Redis server to recreate the dataset by replaying the log file in the event of a crash. However, it can be slower and more resource-intensive than snapshotting.
Overall, Redis persistence is a valuable feature that allows data to be saved to disk and restored in the event of a crash or shutdown, ensuring data durability and availability.


### What are Key-Value Pairs?

In Redis, a **key-value pair** is a data structure that consists of a unique key, which is used to identify the data, and a value, which is the data itself. Key-value pairs are the most basic data structure in Redis, and they are used to store and manage data in the database.

Redis supports a wide range of data types for keys and values, including strings, hashes, lists, sets, and sorted sets. This allows developers to store and manipulate a variety of data types in Redis, such as text, numbers, arrays, and complex data structures.

Redis provides a rich set of commands for working with key-value pairs, such as `SET`, `GET`, and `DEL` for strings, `HSET`, `HGET`, and `HDEL` for hashes, and `LPUSH`, `LGET`, and `LREM` for lists. These commands enable developers to store, retrieve, and manipulate data in Redis efficiently and easily.



### Rich Data Structures

Data structures in Redis are collections of data that are organized and managed in a specific way to support efficient operations. For example, the **string** data type in Redis is a sequence of bytes that can be used to store and manipulate text or binary data. The **hash** data type, on the other hand, is a mapping of field-value pairs that can be used to store and manipulate complex data structures.

Each data structure in Redis has its own unique set of operations that can be performed on it, such as `GET`, `SET`, and `DELETE` for strings, `HGET`, `HSET`, and `HDEL` for hashes, and `LPUSH`, `LPOP`, and `LRANGE` for lists. These operations enable developers to efficiently store, retrieve, and manipulate data in Redis.

Overall, data structures in Redis are an important aspect of the framework, as they provide the underlying foundation for efficient data management and manipulation.

### Benefits of Redis

One of the main advantages of using Redis for caching is its fast read and write speeds. Redis can handle millions of operations per second, allowing it to serve webpages faster than traditional databases. It also offers excellent support for transactions, enabling applications to perform multiple operations atomically. Additionally, Redis supports the use of **pub/sub** channels for fast data sharing between applications.

Redis is highly scalable and can be deployed across multiple machines for high availability, making it ideal for distributed systems that need to process large amounts of data quickly. For instance, Redis can store session information in a distributed system and provide quick access across multiple servers, making it a powerful tool for applications like online gaming, where data needs to be shared efficiently across multiple nodes in real time.

In addition to its performance, Redis offers unique features not typically found in traditional databases, such as **pub/sub** for messaging, **transactions**, and **Lua scripting**. These features enable the creation of powerful applications that are not possible with traditional databases.

### Conclusion

Redis is a high-performance, in-memory data store ideal for use cases requiring fast data access, such as caching, real-time analytics, and session management. With support for rich data structures and atomic operations, it allows efficient data manipulation. Redis also offers persistence options like snapshotting and AOF to ensure data durability. Its flexibility and speed make it a powerful tool for developers looking to optimize application performance and scalability.

### Contact Information

| **Name** | **Email address**            |
|----------|-------------------------------|
| Anugra .W. Lepcha    |  wangchuklepcha801@gmail.com           |

 ### References

| Link                                                                                       | Description                                              |
|--------------------------------------------------------------------------------------------|----------------------------------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9) | Provides an overview of Redis' structure and functions.  |  
| [Redis: What It Is, What It Does, and Why You Should Care - Backendless](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | Explains Redis' importance and typical use cases. |
| [Redis Architecture Notes](https://architecturenotes.co/p/redis) | Detailed architectural insights into how Redis operates. |

