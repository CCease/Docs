[TOC]
# 

# Part 1

# What is Microservices Architecture?

>Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are
>
>- Highly maintainable and testable
>- Loosely coupled
>- Independently deployable
>- Organized around business capabilities
>- Owned by a small team
>
>The microservice architecture enables the rapid, frequent and reliable delivery of large, complex applications. It also enables an organization to evolve its technology stack. 
>
>-Martin Fowler, [microservces.io](https://microservices.io/)



---



## What is Monolith Architecture?

To understand Microservices architecture, we need to first understand how software are developed before the concept of Microservices showed up, and that is Monolithic Architecture.

Monolithic architecture is an architecture that the application is packaged and deployed as a single monolith. For example, a Java application that are packaged as WAR files and deployed on application servers such as Tomcat and Jetty.

Developing in Monolithic architecture is easy as this is how our IDEs and other tool are focus on, building a single application. Application built using monolithic architecture are easy to build, easy to deploy, easy to test and easy to scale, you can just run multiple copies of the application behind a load balancer.

However, everything changed after the application grows and become a huge monster that have millions of codes. Eventually, developers of successful application will continually be adding new features onto the application and it is a matter of time before the application become huge enough to eat all developers.

A  big monolithic application has drawbacks for example:

- Code is hard to understand.
- All-or-nothing deployment.

- Process of development will be slowed down. 

- Hard to achieve continuous deployment.

- Only vertical scaling.

- Limited on current tech stack.

To solve theses problems, the concept of Microservices Architecture is adopted by various organization worldwide including Alibaba, Amazon, eBay, Netflix and more. The idea of Microservices is simple, instead of building a single huge and complex monolithic application, we split the application into smaller services that are **loosely coupled** and independently deployable.

Monolithic Architecture Example:

![Monolitthic Architecture](https://ccease.github.io/Docs/Pictures/Richardson-microservices-part1-1_monolithic-architecture.png)



Microservices Architecture Example:

![Microservices](https://ccease.github.io/Docs/Pictures/Richardson-microservices-part1-2_microservices-architecture.png)

Another example:

![Monolith and Microservices scalling](https://ccease.github.io/Docs/Pictures/MonolithMicro2.jpg)

These services are loosely coupled and independently deployable. The boundary of the services is usually defined by the business capability of the organization to let the services independent from each other. Each service usually has their own databases to further decouple them.



---



## Benefits

The Microservices Architecture can reduce the complexity of the application by decompose the huge monolithic application. If the boundary of the services is defined properly, the services in Microservices Architecture can maintain their part of business capability of the original huge monolithic application while greatly reducing the complexity of the code.



- **Code are more easy to understand.**

  Each service is maintained independently by a team that focus on the services. 

- **Flexible deployment.**

  Microservices Architecture allows each service to be deployed independently, eliminate all-or-nothing deployment.

- **Process of development is faster.**

  The small size of the services let start up and build time of the application become fast and speeds up the process.

- **Continuous deployment is easier to achieve.**

  Microservices Architecture allows each service to be deployed independently and makes continuous deployment more easy to achieve.

- **Horizontal scaling is possible.**

  Multiple copies of a service can be deployed to increase the performance of a specific part in the application. 

- **Can use new tech to develop new features.**

  Services are decoupled from each other, when a new feature is decided to add into the application, a new language or framework that have better performance can be use.



---



## Drawbacks

Even if Microservices Architecture have so much advantage, it is not perfect.

- **Microservices Architecture Application are complex**

  Although the complexity on each part of the application that are decomposed into services are decreased, but the overall complexity of the application is increased. Developers will need to handle the inter-process communication mechanism, deployment, monitoring, update and error handling of the services, service discovery problem and database consistency which are easy to handle on a Monolithic Architecture.


![Amazon and Netflix Microservice](https://ccease.github.io/Docs/Pictures/Frame-25.png)

- **Microservices Architecture requires a clear, distinct and well-defined product.**

  A blur boundary of services may result in dependencies between services and it makes the program has the slow speed and code complexity in a Monolithic Architecture and the difficulty and complexity in the whole application of Microservice Architecture.



To choose to implement Microservices Architecture on the application, we must not forget what the problem that Microservices Architecture are designed to solve, to increase the speed and good scalability possible on the huge application. Although it does bring drawbacks for example increased cost, difficulty and complexity, as long is the problem it aims to solve is solved, it should work fine.



---



# Part 2



# Containers

---

## What is a container?

![Deployment Evolution](https://ccease.github.io/Docs/Pictures/Evolutionofdeployment.png)
Back in the days, organization runs their applications on physical servers. This solution has no way too define resources boundaries for applications in the physical server and cause resource allocation issues. The solution to this problem is to run each application on a different physical server but the resources will be highly underutilized and very expensive for any organization to maintain so many physical servers.

Virtualization was introduced after this. It allows one physical server to run multiple Virtual Machine with defined resources boundaries. The Virtual Machine are separated from each other which provide a level of security. This allows the physical server to better utilize it s resources. The capability of running multiple virtual machine on one physical server also greatly reduces the cost of deploying application. Every Virtual machine is a full machine running all the components including operating system.

Container is something like a virtual machine, but containers have relaxed isolation properties to share the operating system among different containers. This greatly reduce the weight of container and let container portable across clouds and operating system distributions.



---



## Benefits

- Container can be boot in seconds compared to a virtual machine which boots in minutes. 
- Environment of a container remain constant across development, testing, and production.
- Container also greatly improves the resources utilization of a physical server.

The benefits discussed above makes container deployment have much less cost and hassle compared with virtualized deployment. The concept of Microservices, combined with the concept of container, shows software developer a way to deploy to deploy applications in a much convenient way.



---



# Containers Orchestration Tool



## What is it?

Container is only container, what it can do is act as an environment to run your applications. In a production environment, developers need to manage the containers that runs the application and ensure they run as expected, and that is where Containers Orchestration Tool come it place, **it is a tool that automates the deployment, management, scaling, and networking of containers.**



---



## What can it do?

- **Service discovery and load balancing.**

  Containers orchestration tool can expose a container using their name or ip-address and also able to direct traffic, so the deployment works best.

- **Storage orchestration.**

  Containers orchestration tool can mount a storage system according to developer’s choice for example local storage and public cloud providers.

- **Automated rollouts and rollbacks.**

  Containers orchestration tool can create a desired state for containers according to user’s choice. For example, remove an existing containers and adopt all their resources to a new container.

- **Automatic bin packing.**

  User provide containers orchestration tool with a cluster of nodes (hardware that have computing power) and how much CPU and RAM each container needs, containers orchestration tool  will fit containers onto the nodes to make the best use of the resources.

- **Self-Healing**

  Containers orchestration tool restarts containers that fail, replace containers, kills containers that don’t respond to health check and don’t advertise them to clients until they are ready to server.

- **Secret and configuration management.**

  Containers orchestration tool allow user to deploy and update secrets and application configuration without rebuilding the container images, and without exposing secrets in the stack configuration.

- **Scaling or removing containers based on balancing workloads across your infrastructure**

  Containers orchestration tool can create and deploy another instance of a service based on balancing workloads.



---



# Service Mesh

## What is service mesh?

A microservice architecture consist of many services. Each service will need to communicate with other services to work. Due to the large numbers of service in the system, managing these communication is hard. These problems come with a needs of a centralized network management, and that’s what service mesh is aimed to solve.

A service mesh, like the open source project [Istio,](https://istio.io/) is a way to control how different parts of an application share data with one another. Unlike other systems for managing this communication, a service mesh is a dedicated infrastructure layer built right into an app. This visible infrastructure layer can document how well (or not) different parts of an app interact, so it becomes easier to optimize communication and avoid downtime as an app grows.



---



## Benefits

- Increase security in communication between services.
- Tracking of complicated interactions between services become easy.
- Communication between services can be managed in one place.



---



# Conclusion

There is no silver bullet, with every technology we decide to implement on our application, we must always remember the problem that they are designate to solve. When the cost of implement that technology is larger than the benefits it can provide, or the technology cannot solve the problem in our specific environment, we must give up them and not follow the trend.