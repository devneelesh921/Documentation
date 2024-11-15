# Employee API Documentation 

| **Author** | **Created on** | **Version** | **Last edited on** | **Reviewer** |
|------------|----------------|-------------------|---------------------|----------|
| Anjali Dhiman  | 12-11-24      | V1  | 14-11-24           | Shreya Jaiswal |


## Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Architecture](#architecture)
4. [Pre-requisites](#pre-requisites)
5. [Features](#features)
6. [Tools Used](#tools-used)
7. [Database and Caching](#database-and-caching)
   - [1.ScyllaDB](#1.scylladb)
   - [2.Redis](#2.redis)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [Reference Links](#reference-links)

## Purpose
Employee API is a Go-based microservice designed to manage all employee-related data and transactions within the OT-Microservices stack. It provides a centralized backend service for storing and accessing employee information and can run across multiple operating systems, as it is platform-independent. The application requires the Go runtime for execution.


## Introduction

The Employee API is a Golang-based REST API designed for managing employee information. This application integrates ScyllaDB as its primary database and uses Redis for caching. The API is built with the Gin framework, which ensures fast and scalable operations for RESTful transactions.


## Architecture
![image](https://github.com/user-attachments/assets/50d18e52-0e94-48d3-9db7-28ba439e819f)

## Pre-requisites
To get started, ensure you have the following installed and set up on your machine:

- Go (Golang) - Version 1.18
- ScyllaDB - Make sure you have an accessible ScyllaDB instance with the appropriate keyspaces and tables for employee data and RAM of VM (20).
- Redis (optional) - For caching functionality, an active Redis instance is recommended but not required.
These components must be accessible over the network or from within the same environment as the API.

## Features
The Employee API provides several features designed for effective management of employee information and for easy integration into broader systems.

- CRUD Operations: Full Create, Read, Update, and Delete functionality for managing employee records.
- High-Performance Storage: Built on ScyllaDB, a database optimized for distributed and high-throughput workloads, with a Cassandra-compatible interface.
- Redis Caching: Optionally integrates with Redis to cache frequently requested employee data, improving response times and reducing load on the database.
- API Documentation with Swagger: A self-updating, interactive API documentation interface powered by Swagger, allowing developers to easily test and understand available endpoints.
- Scalable and Lightweight: Built with Go, known for its efficiency and concurrency capabilities, making this API scalable and suitable for handling high request volumes.

## Tools Used
This API relies on several powerful tools and technologies:

- Go (Golang) 1.22: The primary language used for development, chosen for its performance, simplicity, and ability to handle concurrent requests efficiently.
- ScyllaDB: A distributed, highly available, and Cassandra-compatible NoSQL database, optimized for low-latency, high-throughput applications.
- Redis: An in-memory data store used for caching frequently accessed data, which can reduce database load and improve API response times.
- Swagger: Automatically generates API documentation that can be accessed and interacted with directly from a web interface.
- Make command: A build automation tool used to automate tasks defined in the Makefile. This is essential for simplifying the execution of repetitive commands, such as building the application or running migrations.
- Migrate: A database migration tool for handling schema changes, which ensures that the database structure stays consistent with the application’s requirements.
- JQ: A command-line JSON processor for handling JSON data.



## Database and Caching
This microservice utilizes ScyllaDB and Redis to efficiently handle data storage and retrieval. Each of these components serves a distinct purpose within the application:

### 1. ScyllaDB
ScyllaDB is the primary persistent database for the Employee API, responsible for storing all core employee-related data, such as employee details, locations, and designations.

### Why ScyllaDB?
- High Performance & Scalability: ScyllaDB is a high-performance NoSQL database compatible with Apache Cassandra but optimized for lower latencies and higher throughput. It is ideal for applications needing quick data access at scale.
- Distributed Architecture: Designed for scalability, ScyllaDB’s distributed nature enables it to manage large volumes of data across multiple nodes, ensuring both high availability and durability.
- Fault Tolerance: ScyllaDB’s architecture supports replication and partitioning, making it resilient to failures and ensuring that data is safe even if a node goes down.
ScyllaDB is chosen for this API to provide a reliable and performant data storage solution capable of handling significant data loads, which is crucial as the employee data grows.

### 2. Redis
Redis serves as an in-memory caching layer to enhance performance by storing frequently accessed data temporarily.


### Why Redis?
Redis operates entirely in-memory, enabling ultra-fast data access, ideal for caching and reducing database load by minimizing repeated ScyllaDB queries. It supports flexible caching strategies, such as Least Recently Used (LRU) eviction, to keep cache data relevant. While optional, Redis enhances API response times, boosting efficiency by caching frequently accessed data.
For a detailed setup, see the (https://github.com/avengers-p11/Documentation/blob/main/OT%20MS%20Understanding/Redis/Redis%20Documentation/README.md#rich-data-structures)

## Conclusion
The Employee API is a robust microservice designed to manage employee data within the OT Microservices architecture. It integrates seamlessly with the Attendance API and Salary API, and leverages ScyllaDB for high-performance data storage. By incorporating Redis for caching, Swagger for API documentation, and Prometheus for monitoring, it ensures efficient operations and scalability. This API is intended to serve as a backbone for employee-related services, providing easy extensibility and maintainability.

We encourage contributions, bug reports, and feedback to help improve the overall functionality and usability of the project. For any issues or feature requests, feel free to open an issue or pull request.

## Contact Information
| Name| Email Address      |
|-----|--------------------------|
| Anjali Dhiman | anjalidhiman.as@gmail.com |

| GitHub | URL |
|----------|---------|
|  Anjaliopstree  |  https://github.com/Anjaliopstree  |


## Reference Links
| Links | Description      |
|-----  |--------------------------|
| https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template | documentation-template |
| https://github.com/OT-MICROSERVICES/employee-api/tree/main?tab=readme-ov-file | Employee api | 
| https://www.simplyblock.io/glossary/what-is-scylladb/    | Scylladb |
| https://www.geeksforgeeks.org/introduction-to-redis-server/ | Redis |
