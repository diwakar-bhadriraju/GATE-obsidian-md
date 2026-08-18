---
title: "Types of DBMS Architecture"
subject: "Database Management System"
topic: "Introduction"
source: "https://www.geeksforgeeks.org/dbms/dbms-architecture-2-level-3-level/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Introduction"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/introduction
---


> [!abstract] Types of DBMS Architecture
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Introduction`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/dbms-architecture-2-level-3-level/)

---

# Types of DBMS Architecture

A DBMS architecture defines how users interact with the database to read, write, or update information. A well-designed architecture and schema (a blueprint detailing tables, fields, and relationships) ensures data consistency, improves performance, and keeps data secure.
## 1-Tier Architecture
1-Tier Architecture: the user works directly with the [database](https://www.geeksforgeeks.org/dbms/what-is-database/) on the same system. This means the client, server, and database are all in one application. The user can open the application, interact with the data, and perform tasks without needing a separate server or network connection.
![single_tier_architecture](assets/single_tier_architecture-cf72718ec3.webp)
DBMS 1-Tier Architecture
- A common example is MS Access. Everything from the user interface to the logic and data storage happens on the same device. The user enters data, performs calculations and saves files directly on their computer.
- This setup is simple and easy to use, making it ideal for personal or standalone applications. It does not require a network or complex setup, which is why it's often used in small-scale or individual use cases.
### Advantages
- **Simple Architecture:** Only a single machine is required to maintain it.
- **Cost-Effective:** No additional hardware is required for implementing 1-Tier Architecture.
- **Easy to Implement:** It is mostly used in small projects.
### Disadvantages
- **Limited to Single User:** It’s not designed for multiple users or teamwork.
- **Poor Security:** Everything is on the same machine, if someone gets access to the system, they can access both the data and the application easily.
- **No Centralized Control:** Data is stored locally, so there's no central database. This makes it hard to manage or back up data across multiple devices.
- **Hard to Share Data:** Everything is stored on one computer.
## 2-Tier Architecture
The 2-tier architecture is similar to a basic [client-server model](https://www.geeksforgeeks.org/system-design/client-server-model/). The application at the client end directly communicates with the database on the server side. APIs like ODBC and JDBC are used for this interaction. The server side is responsible for providing query processing and transaction management functionalities.
![2_tier](assets/2_tier-d6a3de8103.webp)
DBMS 2-Tier Architecture
- On the client side, the user interfaces and application programs are run. The application on the client side establishes a connection with the server side to communicate with the DBMS. For Example: A Library Management System used in schools or small organizations is a classic example of two-tier architecture.
- **Client Layer (Tier 1):** This is the user interface that library staff or users interact with. For example they might use a desktop application to search for books, issue them, or check due dates.
- **Database Layer (Tier 2):** The database server stores all the library records such as book details, user information and transaction logs.
- The client layer sends a request (like searching for a book) to the database layer which processes it and sends back the result. This separation allows the client to focus on the user interface, while the server handles data storage and retrieval.
### Advantages
- **Easy to Access:** Makes fast retrieval.
- **Low Cost:** 2-Tier Architecture is cheaper than 3-Tier Architecture and  [Multi-Tier Architecture](https://www.geeksforgeeks.org/dbms/multi-tier-architecture-of-data-warehouse/).
- **Easy Deployment:** Easier to deploy than 3-Tier Architecture.
- **Simple:** It consists only two components.
### Disadvantages
- **Limited Scalability:** As the number of users increases, the system performance can slow down because the server gets overloaded with too many requests.
- **Security Issues:** Clients connect directly to the database, which can make the system more vulnerable to attacks or data leaks.
- **Tight Coupling:** If the database changes, the client application often needs to be updated too.
- **Difficult Maintenance:** Managing updates, fixing bugs, or adding features becomes harder
## 3-Tier Architecture
In [3-Tier Architecture](https://www.geeksforgeeks.org/dbms/introduction-of-3-tier-architecture-in-dbms-set-2/), there is another layer between the client and the server. The client does not directly communicate with the server. Instead, it interacts with an application server which further communicates with the database system and then the query processing and transaction management takes place. This intermediate layer acts as a medium for the exchange of partially processed data between the server and the client. This type of architecture is used in the case of large web applications.
![3_tier](assets/3_tier-c51fe20334.webp)
DBMS 3-Tier Architecture
**Example:** E-commerce Store
- **User**: You visit an online store, search for a product and add it to your cart.
- **Processing**: The system checks if the product is in stock, calculates the total price and applies any discounts.
- **Database**: The product details, your cart and order history are stored in the database for future reference.
### Advantages
- **Enhanced scalability:** Due to the distributed deployment of application servers. Now, individual connections need not be made between the client and server.
- **Data Integrity:** There is a middle layer between the client and the server, data corruption can be avoided/removed.
- **Security:** This type of model prevents direct interaction of the client with the server thereby reducing access to unauthorized data.
### Disadvantages
- **More Complex:** From 2-tier to 3-tier adds one extra communication point.
- **Difficult to Interact:** This sort of interaction to take place due to the presence of middle layers.
- **Slower Response Time:** Since the request passes through an extra layer (application server), it may take more time to get a response compared to 2-Tier systems.
- **Higher Cost:** Setting up and maintaining three separate layers (client, server and database) requires more hardware, software and skilled people. This makes it more expensive.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/dbms-architecture-2-level-3-level/)

## GATE CS

- Subject: Database Management System
- Topic: Introduction

> [!note] Related notes
>
> - [[Advantages of DBMS over File system]]
> - [[Challenges of Database Security in DBMS]]
> - [[Data Abstraction and Data Independence]]
> - [[DBMS 3-Tier Architecture]]
> - [[Introduction to Database Management System]]
> - [[Need for DBMS]]
> - [[ACID Properties in DBMS]]
> - [[Anomalies in Relational Model]]
> - [[Canonical Cover]]
> - [[Cascadeless in DBMS]]
