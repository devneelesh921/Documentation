# Redis Documentation

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** |
|-----------------------|----------------|-------------|----------------------------|---------------------|
| Anugra W. Lepcha      | 12-11-24       | Version 1   | Anugra W. Lepcha           | 13-11-24           |

---

# Redis: Remote Dictionary Server

**Redis** stands for **Remote Dictionary Server** and was created by **Salvatore Sanfilippo** in 2009 while working on an Italian startup called **Loggly**. Sanfilippo needed a solution to manage large volumes of log data in real-time, which led him to develop Redis. Traditional databases couldn't efficiently handle his requirements, so he created Redis to provide extremely fast data retrieval by storing data in memory.

Initially designed to handle simple key-value pairs, Redis quickly evolved to support complex data structures like lists, sets, and hashes, making it versatile for caching, message brokering, and even primary data storage.

---

## What is Redis?

**Redis** is an open-source, in-memory data store commonly used as a **cache**, **message broker**, and even as a **database**. Its design prioritizes speed by storing data in memory rather than on disk, making it ideal for applications needing fast data access, like real-time analytics, session management, and frequently accessed information caching.

Redis supports various data structures (strings, lists, sets, hashes, sorted sets) and ensures **atomic operations** for consistent and fast data access. 

---

## Why Use an In-Memory Database?

Redis operates as an **in-memory database** by storing data in **RAM**, which allows for much faster data access than disk-based storage. This optimization for speed is beneficial in applications requiring real-time data handling. Example use cases include:

- **Real-Time Analytics**: Financial systems and IoT applications that require instant data processing.
- **Online Gaming**: Real-time player statistics, leaderboards, and matchmaking.
- **E-commerce**: Managing shopping carts, caching product information, and handling high-traffic sales.
- **Social Media**: Quick retrieval of user feeds and notifications.

---

## What is Caching?

**Caching** is a technique for storing frequently accessed data temporarily in a "cache" for fast retrieval. Redis is ideal for caching due to its in-memory nature and high-speed data processing, reducing the load on primary databases by serving cached data.

---
![Screenshot 2024-11-13 145137](https://github.com/user-attachments/assets/f755e6de-2eda-4f0b-842a-50bde5481374)

## How Does Caching in Redis Work?

Redis manages cached data in memory to provide fast data access. Here’s a summary of how it works:

1. **Cache Miss**: If requested data isn't in memory, Redis retrieves it from the main database.
2. **Cache Hit**: If the data is already in memory, Redis returns it instantly.
3. **Cache Update**: New or updated data is stored in memory for future access.
4. **Cache Invalidation**: When underlying database data changes, Redis updates or removes the cached data to maintain consistency.

---
![0_eEt4kTo6zQurjVCu (1)](https://github.com/user-attachments/assets/5a910eee-dcac-474c-bd01-d491e9bf1b56)

## Redis Persistence

Redis offers **persistence** features to store data on disk for recovery after a crash or shutdown. Redis persistence can be configured in different ways:

- **Snapshotting**: Periodically saves the entire dataset to disk. It’s fast but may lead to data loss if Redis crashes between snapshots.
- **Append-Only File (AOF)**: Logs each write operation to a file, allowing for full recovery in case of a crash, though it is more resource-intensive.

---

![durable-redis-2-1200x650](https://github.com/user-attachments/assets/15b8a47d-1cd8-40f1-acb8-0754f338de31)

## What are Key-Value Pairs?

In Redis, a **key-value pair** is the fundamental data structure, where a unique key identifies the data stored as the value. Redis supports various data types for both keys and values, such as strings, hashes, lists, sets, and sorted sets. These data types enable developers to store and manipulate different types of data, including text, numbers, and more complex structures.

Redis offers a range of commands to work with key-value pairs, including:
- **Strings**: `SET`, `GET`, `DEL`
- **Hashes**: `HSET`, `HGET`, `HDEL`
- **Lists**: `LPUSH`, `LPOP`, `LRANGE`

---

## Rich Data Structures

Redis provides diverse **data structures** to optimize data organization and access. Each structure has a unique set of operations that enhance data management and retrieval:

- **Strings**: Store and manipulate text or binary data.
- **Hashes**: Store complex data structures with field-value pairs.
- **Lists**: Useful for ordered collections of strings.
- **Sets**: Hold unique elements without a specific order.
- **Sorted Sets**: Like sets but maintain a specific order based on scores.

These data structures allow efficient and flexible data manipulation within Redis.

---

## Benefits of Redis

Redis offers several advantages:

- **High-Speed Access**: Can handle millions of operations per second.
- **Atomic Transactions**: Supports atomic commands, enabling applications to perform multiple operations safely.
- **Pub/Sub Messaging**: Allows fast data sharing between applications.
- **Scalability**: Redis can be deployed across multiple machines, supporting distributed systems and high-availability configurations.
- **Advanced Features**: Redis includes unique tools like **pub/sub** messaging, **transactions**, and **Lua scripting** for more powerful application scenarios.

---

## Conclusion

Redis is a high-performance, in-memory data store suited for use cases requiring quick data access, like caching, real-time analytics, and session management. It supports rich data structures, atomic operations, and provides persistence options (snapshotting and AOF) for data durability. Redis's flexibility and speed make it an ideal solution for developers seeking to optimize application performance and scalability.

---

## Contact Information

| **Name**            | **Email address**                  |
|---------------------|------------------------------------|
| Anugra W. Lepcha    | wangchuklepcha801@gmail.com       |

---

## References

| Link                                                                                                          | Description                                               |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [What is Redis and How Does it Work? - Medium](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9) | Overview of Redis' structure and functions.               |
| [Redis: What It Is, What It Does, and Why You Should Care - Backendless](https://backendless.com/redis-what-it-is-what-it-does-and-why-you-should-care/) | Explanation of Redis' importance and common use cases.    |
| [Redis Architecture Notes](https://architecturenotes.co/p/redis)                                              | Detailed architectural insights into Redis operations.    |
