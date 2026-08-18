---
title: "Clusters In Computer Organisation"
subject: "Computer Organization and Architecture"
topic: "I/O interface (Interrupt and DMA mode)"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/clusters-computer-organisation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/I/O interface (Interrupt and DMA mode)"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/i/o-interface-interrupt-and-dma-mode
---


> [!abstract] Clusters In Computer Organisation
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `I/O interface (Interrupt and DMA mode)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/clusters-computer-organisation/)

---

# Clusters In Computer Organisation

A cluster is a set of loosely or tightly connected computers working together as a unified computing resource that can create the illusion of being one machine. Computer clusters have each node set to perform the same task, controlled and produced by the software.
Clustered Operating Systems work similarly to Parallel Operating Systems as they have many CPUs. Cluster systems are created when two or more computer systems are merged. Basically, they have an independent computer but have common storage and the systems work together.
The *components of* clusters are usually connected using fast area networks, with each node running its own instance of an operating system. In most circumstances, all the nodes use the same hardware and the same operating system, although in some setups different hardware or different operating systems can be used in some setups.
In the field of computer organization, a cluster refers to a set of interconnected computers or servers that collaborate to provide a unified computing resource. Clustering is an effective method to ensure high availability, scalability, and fault tolerance in computer systems.
Clusters can be categorized into two major types, namely high-availability clusters and load-balancing clusters. High-availability clusters guarantee uninterrupted service provision even when one or more nodes fail. Multiple nodes are configured to provide redundant services, so that in case of failure, another node takes over the failed node's services without any interruption to the user. On the other hand, load-balancing clusters distribute workloads among nodes in the cluster to ensure that no single node is overburdened.
Several hardware and software technologies can be used to implement clusters, including dedicated clustering hardware, virtualization technologies, and distributed software frameworks.
Clustering provides several benefits such as high availability, scalability, fault tolerance, and load balancing. Nevertheless, there are a few challenges associated with clustering, such as complexity, cost, and management.
To ensure the best performance on SEO, the content should contain relevant keywords and provide valuable information to readers. It is important to avoid keyword stuffing and provide content that is easy to read and understand.
![](assets/Screenshot-from-2018-03-22-21-10-14-877a6c8749.png)
For making cluster more efficient there exist two clusters:
- **Hardware Cluster**
- **Software Cluster**
**Hardware Cluster** helps in enable high-performance disk sharing between systems, while the **Software Cluster** allows all systems to work together.
![](assets/Clustered-300x259-880b4b514f.png)
**Types of Cluster Systems:**
Primarily, there are two types of Cluster Systems:
- **Asymmetric Cluster:** In this type of clustering, all the nodes run the required applications, and one node is in hot standby mode. The Hot standby node is used for monitoring the server till it fails, when it fails then it takes its place.
- **Symmetric Cluster:** In this type of clustering, all the nodes run applications and monitor other nodes at the same time. This clustering is more efficient than Asymmetric clustering as it doesn't have any hot standby key.
**Classification of Clusters:**
*Computer Clusters* are arranged together in such a way to support different purposes from general-purpose business needs such as web-service support to computation-intensive scientific calculation. Basically, there are three types of Clusters, they are:
- **Load-Balancing Cluster** – A cluster requires an effective capability for balancing the load among available computers. In this, cluster nodes share a computational workload to enhance the overall performance. For example- a high-performance cluster used for scientific calculation would balance the load from different algorithms from the web-server cluster, which may just use a round-robin method by assigning each new request to a different node. This type of cluster is used on farms of Web servers (web farm).
- **Fail-Over Clusters** – The function of switching applications and data resources over from a failed system to an alternative system in the cluster is referred to as fail-over. These types are used to cluster database of critical mission, mail, file, and application servers
- **High-Availability Clusters** – These are also known as “HA clusters”. They offer a high probability that all the resources will be in service. If a failure does occur, such as a system goes down or a disk volume is lost, then the queries in progress are lost. Any lost query, if retried, will be serviced by a different computer in the cluster. This type of cluster is widely used in web, email, news, or FTP servers.
**Benefits:**
- **Absolute scalability** - It is possible to create large clusters that beats the power of even the largest standalone machines. A cluster can have dozens of *multiprocessor machines.*
- **Additional scalability** - A cluster is configured in such a way that it is possible to add new systems to the cluster in small increments. Clusters have the ability to add systems horizontally. This means that more computers may be added to the clusters to improve their performance, redundancy, and fault tolerance(the ability for a system to continue working with malfunctioning of the node).
- **High availability** - As we know that each node in a cluster is a standalone computer, the failure of one node does not mean loss of service. A single node can be taken down for maintenance, while the rest of the clusters takes on a load of that individual node.
- **Preferable price/performance** - Clusters are usually set up to improve performance and availability over single computers, while typically being much more cost-effective than single computers of comparable speed or availability.
### Features of clusters in computer organization:
**High Performance:** Clusters are designed to provide high performance computing by utilizing the processing power of multiple computers working together.
**Scalability:** Clusters are scalable, which means that they can easily accommodate new nodes or computers to increase processing power and performance.
**Fault Tolerance:** Clusters are designed to be fault-tolerant, which means that they can continue to operate even if one or more nodes fail. This is achieved through redundant hardware, software, or both.
**Load Balancing:** Clusters use load balancing techniques to distribute processing workload across multiple nodes in a balanced manner. This helps to maximize performance and prevent overloading of individual nodes.
**Interconnectivity:** Clusters are interconnected through a high-speed network that allows for efficient communication and data transfer between nodes.
**Shared Resources:** Clusters allow for shared access to resources such as storage, memory, and input/output devices. This makes it easier to manage resources and reduces the need for duplication.
**Cost-Effective:** Clusters can be cost-effective compared to traditional high-performance computing solutions. This is because they use commodity hardware and software, and can be built using open source technology.
**Versatility:** Clusters can be used for a wide range of applications, including scientific computing, data analysis, and web serving.
### Advantages and Disadvantages
1. When considering a particular topic, it is important to evaluate the potential advantages and disadvantages. This approach provides a comprehensive understanding of the topic, helping to make informed decisions.
2. Advantages refer to the benefits or positive aspects of a particular topic. For instance, when implementing a new technology, the advantages may include improved efficiency, cost savings, and increased productivity. These benefits can positively impact individuals or organizations, leading to increased profits, better customer service, or improved quality of life.
3. On the other hand, disadvantages refer to the potential drawbacks or negative aspects of a topic. When evaluating a new technology, for instance, the disadvantages may include higher costs, reduced privacy, or possible security breaches. These drawbacks may negatively impact individuals or organizations, leading to financial losses, negative customer experiences, or reputational damage.
4. It is important to weigh both the advantages and disadvantages of a particular topic before making a decision. This helps to ensure that the potential benefits outweigh the potential drawbacks. Additionally, it is essential to keep in mind that the advantages and disadvantages may differ depending on the individual or organization's needs, goals, and circumstances.
In summary, evaluating the advantages and disadvantages of a topic is a crucial step in decision-making. By considering both the positive and negative aspects of a particular topic, individuals or organizations can make informed decisions that align with their goals and values.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/clusters-computer-organisation/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: I/O interface (Interrupt and DMA mode)

> [!note] Related notes
>
> - [[AI, ML & Data Science]]
> - [[Aptitude]]
> - [[Asynchronous input output synchronization]]
> - [[BUS Arbitration]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Computer Ports]]
> - [[Connect]]
> - [[Corporate Solution]]
> - [[CS Core Subjects]]
> - [[DevOps]]
