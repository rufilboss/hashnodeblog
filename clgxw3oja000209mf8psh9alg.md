---
title: "Day 71 - Introduction to Microservices"
datePublished: Tue Apr 25 2023 16:07:24 GMT+0000 (Coordinated Universal Time)
cuid: clgxw3oja000209mf8psh9alg
slug: day-71-introduction-to-microservices
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1682512216138/b7204520-ed8b-45cc-aeb7-10132f4365e6.png
tags: microservices, software-architecture, devops, 100daysofcode, 2articles1week

---

**Microservices** is a software development approach that has gained immense popularity in recent years. It involves breaking down a large monolithic application into small, independently deployable services that work together to provide the required functionality.

Microservices offer a wide range of benefits, including increased agility, scalability, and resilience. In this blog, I'll provide an introduction to microservices and explore the key differences between microservices and distributed systems.

# What are Microservices?

**Microservices** is a software development approach that involves breaking down a monolithic application into small, independent services that communicate with each other through APIs. Each microservice is responsible for a specific task or functionality, and they work together to provide the required functionality of the application.

Each microservice is developed and deployed independently, allowing teams to make changes and updates without affecting the entire application. This approach enables teams to be more agile and responsive to changes in business requirements.

## Key Features of Microservices

Microservices offer a wide range of features that make them an ideal choice for modern software development. Some of the key features of microservices are:

1. **Independent Deployment:** Each microservice is developed and deployed independently, enabling teams to make changes and updates without affecting the entire application.
    
2. **Decentralized:** Microservices are decentralized, enabling teams to develop and deploy them independently.
    
3. **Resilient:** Microservices are designed to be resilient, enabling them to continue functioning even if one or more microservices fail.
    
4. **Scalable:** Microservices are highly scalable, enabling teams to add or remove microservices as required to meet changing demands.
    
5. **Technology Agnostic:** Microservices are technology-agnostic, enabling teams to use the best tools and technologies for each microservice.
    

## **Microservices vs Distributed Systems**

Microservices are often compared to distributed systems, but they are not the same thing. While both *microservices* and *distributed systems* involve breaking down an application into smaller components, there are some key differences between the two.

Distributed systems involve breaking down an application into smaller components, but these components are still tightly coupled and often rely on a centralized database. In contrast, microservices are loosely coupled and communicate with each other through APIs.

Distributed systems are often developed using a single technology stack, whereas microservices are technology-agnostic and can be developed using different technologies and programming languages.

In a distributed system, changes to one component can often have a ripple effect across the entire system, whereas in microservices, changes to one microservice do not affect the entire application.

# Conclusion

Microservices is a revolutionary approach to software development that enables teams to be more agile, responsive, and scalable. It involves breaking down a monolithic application into small, independent services that work together to provide the required functionality.

Microservices offer a wide range of benefits, including independent deployment, decentralization, resilience, scalability, and technology agnosticism.

While microservices and distributed systems are often compared, they are not the same thing. Microservices are loosely coupled and communicate through APIs, whereas distributed systems are often tightly coupled and rely on a centralized database.

Another key difference between microservices and distributed systems is that microservices are often developed and deployed independently, whereas distributed systems are typically developed using a single technology stack and deployed as a single unit.

In a microservices architecture, each microservice is responsible for a specific task or functionality, and they communicate with each other through well-defined APIs. This approach enables teams to develop and deploy each microservice independently, without affecting the entire application.

This level of independence and autonomy is not possible in a traditional distributed system, which is often tightly coupled and relies on a centralized database or middleware for communication between components.

Another advantage of microservices is that they are designed to be resilient. In a microservices architecture, if one microservice fails, the other microservices can continue to function independently, enabling the application to remain operational despite the failure.

Overall, microservices offer a range of benefits over traditional monolithic or distributed systems, including increased *agility, scalability, resilience,* and *technology agnosticism.* By breaking down a large application into smaller, independent components, teams can respond more quickly to changing business requirements and deliver new features and functionality more rapidly.

***PS:*** *I am continuing the 100DaysOfDevOps challenge that I started last year, picking up from day 71 as I encountered a roadblock on day 70. My focus for the next 30 days is to delve into the topic of microservices. Additional information about my challenge is available on my GitHub repo at the following link if you're interested. See the repo(it contains the documentation of the challenge from day 1)* [*here*](https://github.com/rufilboy/100DaysOfDevOps)*.*