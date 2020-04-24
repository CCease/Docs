# What is Microservices Architecture?

In a short sentence, Microservices is an architecture, an approach in which a single application is composed of many loosely coupled and independently deployable smaller services.

Before we get to know more about Microservices, we need to understand how the term Microservice come out and what problem this architecture is designed to solve.

The term "micro web services" was first used by Dr. Peter Rogers during a conference on cloud computing in 2005. "Microservices" themselves premiered at an event for software architects in 2011, where the term was used to describe a style of architecture that many attendees were experimenting with at the time. In 2014, Martin Fowler talked about Microservices and the term begins to get a lot of attention.

## What is Monolith Architecture?

To understand Microservices architecture, we need to first understand how software are developed before the concept of Microservices showed up, and that is Monolithic Architecture.

Monolithic architecture is an architecture that the application is packaged and deployed as a single monolith. For example, a Java application that are packaged as WAR files and deployed on application servers such as Tomcat and Jetty.

Developing in Monolithic architecture is easy as this is how our IDEs and other tool are focus on, building a single application. Application built using monolithic architecture are easy to build, easy to deploy, easy to test and easy to scale, you can just run multiple copies of the application behind a load balancer.

However, everything changed after the application grows and become a huge monster that have millions of codes. Eventually, developers of successful application will continually be adding new features onto the application and it is a matter of time before the application become huge enough to eat all developers.

Once the application has become a huge and complex monolith, it will be too large for a single developer to fully understand every line of the code and bug fixing and implementation of new features will be difficult and time consuming.

Besides, a large application will also slow down the process of development. The larger the application is, the more time it takes to start and build the application. According to what NGINX stated in their blog, some developers reported start-up times as long as 12 minutes and in some cases, it might even take up to 40minutes to start up. It will be a huge waste of time if developers need to regularly restart the application server.

Another problem with a large monolithic application is that it makes continuous deployment very hard to achieve. To deploy a small change in a part of the application requires the whole application to redeploy as it is deployed as a whole. This will greatly impact the efficiency of software development as the deployment time for a huge application will also be long.

Monolithic application is also difficult to scale when different modules have conflicting resources requirements. For examples, one component requires intensive use of CPU while another module requires a better RAM to perform better. When the environment is unable to provide pump up CPU and RAM resources (For example different instances provide by Amazon EC2), performance of one module won’t be able to increase.

Finally, monolithic application makes it difficult for developers to shift to a new language or framework even if it is a better choice. Just think that you have a huge and complex application with millions of codes, it would be a nightmare if someone were to rewrite the entire application using another language or framework.  

To solve theses problems, the concept of Microservices Architecture is adopted by various organization worldwide including Alibaba, Amazon, eBay, Netflix and more. The idea of Microservices is simple, instead of building a single huge and complex monolithic application, we split the application into smaller services that are **loosely coupled** and independently deployable. These services communication with each other through combination of RESTapi.

Monolithic Architecture Example:
![Monolitthic Architecture](https://lh3.googleusercontent.com/RighWaOyAzrf_bOG7Sgs2RktGJQgYsl_IGJDuIbllAF7_yI_a2AgC6KEjP4Qv8I--q1S0I9AF9vXkJ5_6FgQHksVdRDFRKD6c09yl9ZR8Vg_dNB1lgGkwF8cOMiXwKidqTqf9dILbbcDvIHKRBL8b8dS0LyYnSmwju4qjN6_kl3xCf9gvJ3XGUA3GrOJkSz8ZNV3LcUTJEAO6V_0w3pBUvV5dZGAbxVidE3UtLyufeGiOBJK9Y0ol2RHeJD8JNynjA2KHZOTjpT7-U9r39kzkJpDom82tyvO4cfU36dKEGDBVXgAf-4EsPBSOW_W-_-DTGEr1Z8y_P0imDGiI2YjBVjK6Bjq3mQlfGGqUtUtyBKKPmMlPBu9mTp_H26bYbxR4OZg_gSm1sDXySej-DaaBCnxom6hLAjnsgHeNiQXkqxUGgsFRMD9DV0TC7DR0qSqkmKI0vackA7uUHCaS5P28m-g_Mncm9dByWeTVUwjMwLSdJ0MJ4eThz976pvF2aj9TchRl2Cqb-f4ymT0cvhcdWVGvzuE3NQYxF0UouOOeo_XphY5l5m5klMiybVG2oPQv3lSEuyaNZiYMkEqjrpZ4c_fFHlAH6I8IrGwxKmonSjfwxU4C-5e-CU751HtwuFcQeObw_1Vd-5AAHV7NiZ1C2GH89aI9raSc-9_-sXVvjtho-nmI6kK_RFZ__diDGytU0WKy0pZslmfKGymjDTDDQR1TQaVv63X4yp4RNO2LSH4nF5Vt5Vo=w767-h810-no)



Microservices Architecture Example:
![Microservices](https://lh3.googleusercontent.com/ZC7LPKnMRLJPkIkOTEpe1hwSXcKmASLdihZycX6v0cXTENtAYg062nMkdHElwnrFhCXoLKvR5L71__Y6Slf_2Ljnqqak_HZisA7UmTGHNdt6rHiffVM9viFv-_Dt9T_udUuGdQPNMwcZqo9XyvqTrE6_b_JUDGbl7YXCJppw2ytGQpZ8WaParRQrjR45wDXLZdVbcf-63Ha8pWi55dRhJfR_4mPpAO5_wZC4P9l7IpNRARul3Vrg9C2fyafp4mcjhk7TJs8kTjtzG5T3kJgI-0Oga3ASDhUX_zu2iMEX912UP4hAUhJOjx98dRu_a7SQ-v6WpFXYKpzy4GGdhh01WVFnNUNV5TXn47b0L1BF1AgwZBwS5eEBDGRrcoEbOYksnh3n24Vspgm1kIiSzkwLTjoP07IM0jGkRtWJXdWsKyiMaamvc0PRO9724V1C8DL_ViVCK6zjLpyzZrmDwfJvCGpxQdFhpmsa6Mkq0jt__3EPdZuwbe3_JNhOsxym0rDbg0VoSI7NlNi9yl0fCKqX5zytoV05VFS_fU7nooju4ovxlGba6IfG7FOfh14N-lA3Sp2OyL7Zm0qBeE4rfQDbRUgtW5OMHIjfPg6iu2loug9jfpLx-r6hFtnZOF5JEFb3tl8xQh0uZP37U201egkfVaJOmyH--1gd015niMtP9kTmWEvK4o3-dVqiO2I=w815-h832-no)


These services are loosely coupled and independently deployable. The boundary of the services is usually defined by the business capability of the organization to let the services independent from each other. Each service usually has their own databases to further decouple them.

## Benefits of Microservices Architecture

The Microservices Architecture can reduce the complexity of the application by decompose the huge monolithic application. If the boundary of the services is defined properly, the services in Microservices Architecture can maintain their part of business capability of the original huge monolithic application while greatly reducing the complexity of the code.

In microservices architecture, each service is maintained independently by a team that focus on the services. The small size of the services let start up and build time of the application become fast and saves time. Also, because the services are decoupled from each other, when a new feature is decided to add into the application, it can choose to use a new language or framework that have better performance. Furthermore, if the team decide to use a new language or framework for the service they had already written, they can simply rewrite the service because the service is small.

The Microservices Architecture also allows each service to be deployed independently. Developers can observe the impact of the changes rapidly and thanks to the small size, the deploy speed is also fast. This makes continuous deployment possible.

Last, Microservices Architecture enables each service to be scaled independently. Multiple copies of a service can be deployed to increase the performance of a specific part in the application. Also, services can be deployed to different environment and the conflict in resources requires by different services will no longer exist.

## Drawback of Microservices Architecture

Even if Microservices Architecture have so much advantage, it is not perfect. The most significant drawbacks of Microservices Architecture are the complexity it brings to the application itself. Although the complexity on each part of the application that are decomposed into services are decreased, but the overall complexity of the application is increased. Developers will need to handle the inter-process communication mechanism, deployment, monitoring, update and error handling of the services, which are easy to handle on a Monolithic Architecture.
![Amazon and Netflix Microservice](https://lh3.googleusercontent.com/4mPgsTINaEDEUTgSo_lpOgiFnPKh4UNF0tuA_LfKsfcw_ySnvVnlDzd5NyI2v5tIbfVgqnlicH_QO7GJ_8u1bSFEvynOmhvjASbleRYMj3MdNaA6GNscN74VM0D1MQDcUWZw9Bhhh-mCJS5R_t2W63HwgV-3nEgyH-BWCRzg6SepkcsjIyv_AxC0lHSSMXSvZ30E1MLzKzXxG2GoVPtFSaldRsAr5gFZLNAUHuE4vR-bo5vnUaORgn8AUT_CCI_ZRazmDxFlHbY-5tMxF95Mu9eLDVV0EHnMs10Brz42IFKMCo71d6ycQAIgLw5dwTQlaAY1GOVzrAjXef6UMQxUX-NVy-yEME6M3DdDNNzKli33K5oCsrM0K-wkNH4AfRCO5L6LL6Me3g9XCVtJKMV09r5vF7YrIlOrXy9fyj8dBb2trzaEt2rJgKS30fV0_asMgO4RVxHzxpZsghIG4Sk7kywNNUVRfdDUobvf3OEZesH58insmL4MV6d0LpQ9yyWkU7dazWHyASZMIB7NuJqyOAgIws_NDk8cmPUKCUYL0Vb4TTD1YoHX0mLIfy8KzC-XGM0UCbyobhIqjphLNUa4wO_6TMAm5rnka7p0crhVXFMrvO9ATDcwOsq-6vSKSNwJzAs-_0skUiL8fui9jGLvGSlY0YzxehhDnOrNKtGg_2df7N1vJneY_hetr_A=w1200-h628-no)

Another major drawback of Microservices Architecture is that it requires a clear, distinct and well-defined product to decompose the application into different services. A blur boundary of services may result in dependencies between services and it makes the program has the slow speed and code complexity in a Monolithic Architecture and the difficulty and complexity in the whole application of Microservice Architecture.

To choose to implement Microservices Architecture on the application, we must not forget what the problem that Microservices Architecture are designed to solve, to increase the speed and good scalability possible on the huge application. Although it does bring drawbacks for example increased cost, difficulty and complexity, as long is the problem it aims to solve is solved, it should work fine.

# Why Microservices Are Viable? – Docker

Although Microservices Architecture can solve the problems of a Monolithic Architecture, Microservices Architecture are only adopt by big names in the market for example Netflix, which had successfully moved to the cloud, breaking up their monolith into hundred of fine-grained microservices by December 2011.

![Trend of Microservices](https://lh3.googleusercontent.com/LiJMM6gUeNAXEydGgTW_TBd-SZXeYZAg5c--gZt293CcxDIYeA7aBnr_ZQ_XVdBXQwmVY0KSfjacITQnCQIH_81_0dq0pzu_zvzlsaZLQLXmizWeLWTcKjtnPsafIRAIAE5gtfR9FtJsG4wNYkVa9ElOaaC97XdaqHoUAb-Vonfc_AHnku5F8Niez2HxmBquIKevUEX2YNxMqWMJk1qk9KTbcFAdpT0iDdQ0xEa93SG65_F9NI-3M-QUjBwrKb5g8CZXjdyxQvrPvULUHyweeUxkKt55VSTmy-4i4cshKVvrhJXMUoRk1IP0AG2HgGv62n7lMiAxTJeHXluEat-0NCWjK0ajDwVA078oZL9kCdbO9QALPCdXr4A_-SfwkfhDXlY-whsEHNEfj8Etb1K_dH4qoxdLPhCGs8M2uTISHMk-tneqFjPURk2elm8yr2hlOSqQUoS2bR2kf3j-zd0kWE6oXqKSDb5pW7FRXf1BNb2wOYPE6K-u2AHCJCndXS3WS_SBWPbegZ5wQyOaR9WqsCih3OY2iR-7XYHI6w67RiDV1sAQZMYub4Bdukkm8DuXXuB54LVzAUfUXab8dYaDQmwlD6U393W3UUhkfFWW3ZeJD3lcykaUdcL6mVXCcg41I0DMi5-h9GZquXp6Fk9w1eKjYdDExHuMoodzpqiNYiibWnuQcbOJ5I3E5EA=w1186-h424-no)
It was only until 2014 that the Microservice Architecture are getting popularity and software developer start to consider Microservice Architecture to be viable. The reason behind this is suspected to be the popularity of docker. To be simple, docker is a solution to build and share container, but what is a container?

![Deployment Evolution](https://lh3.googleusercontent.com/QyoVJTnC_oFIhm6XGpu68cDgxfHqBDxLQpl6yIQNu9cFihmP-j8uFCQRGPQ-Jp2Ms-m6AzYo-dXGmCTpItj6VuWT3fCXt0ZmIkV0zHonOaTFg4fGTPk-ifFJkG-SJfbDQuuueYFfpbbI5iuGZHW_Xlx5OCrpAgbSD8CNiCW8YDXWZ7him1atNScvhSP0RvcWnTRacUhzdhyK8XSJj3wwYHqvUwvZsQ2oHemlQvdT861dkbTviTqRx57SilyoMPVWF-mTUkD-bf_6pW1X_mhN09YgHqKxAS2_AbNv51i3-7Bp8J67BuNX5po9wTmmljiWybuboyW0r5wwz4U1HjGK8sFBWl-V0RUcIIxVa3o4MDbrOfmxe48f70k3IZYxp4xvlb2EvHUvVrrdj3CiyTPbYgwbkK3_6tP0nGCdoEKi1oP6a1KbP7BsRxfC085HB3Nw_8KcauTUT8J-spm4R1R6V92knZqDdh35AnnajR8N_kxZLEkt1NSDyTyZINE8CkT7VtBspmOLD_KQ6iZFtnFyAoMwuwYJalLDv4xyUbdokhvmw-ODMKqQHemwY5cXBNAmihTZDSuXOG57OU8dLeUpil_rmkWD3QqAE7nVijVaYYo_fUmRsJrKwdVb2_MIloaO8Dsj1Nh3eYq6BhyToh4wKcRL8SwqWTVHwFNW0_OcRVW8GvusgmtNur3SXv4=w714-h299-no)
Back in the days, organization runs their applications on physical servers. This solution has no way too define resources boundaries for applications in the physical server and cause resource allocation issues. The solution to this problem is to run each application on a different physical server but the resources will be highly underutilized and very expensive for any organization to maintain so many physical servers.

Virtualization was introduced after this. It allows one physical server to run multiple Virtual Machine with defined resources boundaries. The Virtual Machine are separated from each other which provide a level of security. This allows the physical server to better utilize it s resources. The capability of running multiple virtual machine on one physical server also greatly reduces the cost of deploying application. Every Virtual machine is a full machine running all the components including operating system.

Container is something like a virtual machine, but containers have relaxed isolation properties to share the operating system among different containers. This greatly reduce the weight of container and let container portable across clouds and operating system distributions.

Container are popular because they provide multiple benefits to developers. One of the major benefits is the performance of container. A container can be boot in seconds compared to a virtual machine which boots in minutes. Another major benefit is the environment consistency across development, testing, and production. A container consists of library and dependencies and combined with its lightweight, a container will be built during development, testing and deployment while maintaining the same environment. Container also greatly improves the resources utilization of a physical server as more application can be deployed onto a physical server using container deployment compared with virtualized deployment.

The benefits discussed above makes container deployment have much less cost and hassle compared with virtualized deployment. The concept of Microservices, combined with the concept of container, shows software developer a way to deploy to deploy applications in a much convenient way.

## How docker?

As discussed above, docker is a way to build and share container. In short words, docker can create a docker image, which is an image of a container. The image can be run on different machine and environment to create a container, which are identical to the container that the image is created from. This help software developers a lot as we now have hundreds or thousands of services need to be developed, test and deploy, and they all have different dependencies.

# Container is only container – Kubernetes

Container is only container, what it can do is act as an environment to run your applications. In a production environment, developers need to manage the containers that runs the application and ensure they run as expected, and that is where Kubernetes come it place, it is a framework to automate application deployment, scaling and management, also known as container-orchestration system.

## What can Kubernetes do?

Service discovery and load balancing.

- Kubernetes can expose a container using their name or ip address and also able to direct traffic, so the deployment works best.

Storage orchestration.

- Kubernetes can mount a storage system according to developer’s choice for example local storage and public cloud providers.

Automated rollouts and rollbacks.

- Kubernetes can create a desired state for containers according to user’s choice. For example, Kubernetes can remove existing containers and adopt all their resources to a new container.

Automatic bin packing.

- User provide Kubernetes with a cluster of nodes (hardware that have computing power) and how much CPU and RAM each container needs, Kubernetes will fit containers onto the nodes to make the best use of the resources.

Self-Healing

- Kubernetes restarts containers that fail, replace containers, kills containers that don’t respond to health check and don’t advertise them to clients until they are ready to server.

Secret and configuration management.

- Kubernetes allow user to deploy and update secrets and application configuration without rebuilding the container images, and without exposing secrets in the stack configuration.

## How?

![step1](https://lh3.googleusercontent.com/Wi59IsZYrmb_aIWdyKlQapEV_LSdn-_8Ohidviqvu3Oc1uO2snblDZV7YFuvfN8dt7BvJROOI9Uk1SGKMaGXOwaV1Mj7qLf0-SGf6TTzj3GdktqcVy2eKFdcPe51lc73bkz46jpIioP-PgQfY5kdP-PHaK4oODUOBX3Im8nlxjZlP9hTnWAz0Z65bX0yXmBqZanqofTSYlOcuuLLaEheJpiSoxEYcyh-jnIFCA-yI7w6zPOdPvyV2a8cieq28WzXCbf76yL4UkZTHGrRXs-Zq932WdAxbihoi0DI3ZYm_ywcS3jKF8ciduK9FR51uNHH76CdKoIzo5sPAZImeaq7k2uGY05oXEdQxhnJBjBCUTYIB7c7oPkCIvcEksnQ5-Gzaa_kU7Oj1w3n4KbQNP-eUi08vvywzqSYss5EopBJoD5uN1PwAaYsxvMfnGlWS5d_OSYLwA2lnvOXjRjHDSeQdfQp0CBXoV0TfQSf0AzYa1qEmCwM48vbkuEjG40IfUejI_LylxsWaRs2zqCOFlTrw-ueA4mYFmIBnbmtr6ZuLvFjwoShmzdMFk8uGW8fuFskZyThFO4Z96UOpGdaLsst11oupOUk1nhdxvYJn7Aq34IDl-O_O_ZBHu7GKdDYTUYOWzMWHpY8Seyq3FJPF090rpplBY3H1JQ0Yh2VD5RjM1ONgVWVs26JDb7IFcM=w719-h293-no)

Let’s first look at the components of Kubernetes. Node is a hardware that we can deploy our application on, like a server. Masternode is where Kubernetes manage the pods and nodes. Kubectl is how Kubernetes tell masternode user’s configuration.

Now, I want to create a pod, with my front end component inside, and with label a:f (application : front-end), so I write what I want inside a yaml file (call manifest in Kubernetes) and push it through kubectl. It will hit the api running on masternode, and masternode will talk to kubelet (A component responsible to scheduling and make sure apps are healthy and running within the node, exist in every node.) in one of the node, and the pod a:f will be created, as show on diagram above.

![enter image description here](https://lh3.googleusercontent.com/1X9rtQpUg723DGothvvQEYRGQfnicNPwQs4SnO8BJoZPfsJnuFGwMU5g4x70mYajb4lISw99LGA940QLFEteqXbUq9NKLvrpV9Z9RI7NRTzLYcofV4kxOa6fEXY9Z6SdNxOKpuMwF0YKt_d6pRyyRdAH06myV7foXvANLFrquoSEDgyttDLALqlbeWich-BrcX576nVE3JvOnIbw-CTbwKDja81OcLxWar3_7t6xLNug7zEXUw_cByHmN0GmYioAvyitSFuC47qXS0LG9YvczWatqnywv3jCMIk8K9GJ4fDNY5oP7Ip3Uc4LUw18veV-GTW3vJim28m3CNkw8jOgNo78mtRCyvnUMzLBxMtdPMgRm3zdTuLGInfSxSHVbvDg-qo19sJpfc-XcxoVi4mpwcE7odtzXR00-yJIWpPuTRumuvFdlC2tPT6BUx6JlKg83YxP5VT9zcnIkydSdNkfS33fsvSiHb4TieA2QFOmGXNzU2jXIJjcwbMfw9a0M1pVNo9-0aIPwknpsLGV4VpwQDvBiJ9xYiglON-zs4WOksDBpzhSeK7F1lmPdnLrdKNZCnSDYAzomxzIJLXpsh_QRN8pTAphj4gAzw9RAJx-2j-MajrBNNmXbXNgJO0IeoM5oBkuAZskv4wRL3CRnkWxu0-1c81NZMWZPFXDbdqygRV3piFlfyzFe1SE-5Q=w1257-h521-no)

So now I want to deploy 3 of my front end components and 2 of my back end components and keep them running. After I complete the yaml file and it hits the master node, the master node will keep record of the deployment and make sure it works well. From the diagram above, the master node notice that only one front end component is deployed, so 2 more front end component and 2 more back end component are deployed.

![step3](https://lh3.googleusercontent.com/0nmEj-zDQOvmFqgtZxWp9xxIjMlG0tdJXAw5C0rrawpERlyfwUX0-iFWlNsqDaMggBhv9s7MNqEklCMO0yugw72v64yR3y7b6MAMNonTZwWAcPgygjRwAOqDfS5iaz84OZuVvQFwNiLPLOvcDAGVRtA7xWq2WnUjg2VUqB_INaEwKyCHI7v1BoVkBufrineSMAuG6CEHmqrP6HXP2bd-CCnXCoxIDbiyGknfFq7_7evKAPNU9DGPlof4J9yFh7hndZLMTJt4q-hT3T30sXOnBcyKVa5dfU7S9GF05Jo1YbbiK_cPp-EhSEFxL57Hg3TEgmLNPo0ayfQ7EgZnrcXJRP5f-oZlljUqDfUzuanOnNxxxbUnOGyauj6tXOGofW_szd02vil4MNLY9voDsZbkydBQIYsCvBwnfv5awb17c0pJFUDjHW7TIYpoKTNWyWQ_m2Gb3u72MnMY2bj5YEEcfqsw5G-RvwVPbRZOqxGz92wNKmqfok_vdgfjVLkq6N6ssFvwRtYGN1d6FOMarpFl5oJrZzHFkx5gSaSLwiawNUjRrksFcfaFL_zTxK92SPxKlW21kDueWxUDXobEQ0fWorMoPnf6hmiAuO3s7Zh_505eLXvNRlH7ZiQnwjjmt7DFxzMr-W0eqXWn7JmiMhgR6HjTQoqHC5oK7mbqa_nEptV1rE1Jvj0YAN6kHXE=w1244-h508-no)

Above is the basic flow of how Kubernetes deploy and manage the services. Kubernetes can also expose the ip of the services to let end users access the services by writing the yaml file.

# What is service mesh?

We talked about microservices architecture, and how the services are deployed and being orchestrate by Kubernetes, now we investigate how the services communicate with each other.

Services talks to each other and act together as a system to complete their job. In the communication of the system, a developer will want the connection between services to be **secure**, for example using TLS. They also want to dynamically configure how the service is **connect**ed to each another, for example they implement a new version of UI and want to direct 10% of the traffic to the new version of UI. Off course, developers will also want to **observe** and monitor the traffic flow in the system to find out the status of services and the bottleneck of the system. Also, they might want to **control** the communication between services by not allowing certain services talk to another services.

We know that Microservice Architecture consist of many services. The things stated above need to apply to every service. Due to the large numbers of service in the system, there might be times where developers forgot or make a mistake somewhere, and they will require a hard time to find out where did it went wrong. These problems come with a needs of a centralized network management, and that’s what service mesh is aimed to solve.

## Istio

Istio, is the solution for service mesh, it makes developers easy to create a network of deployed service with few or no code changes in the service code. Istio done this by inject a special sidecar proxy throughout the system that intercepts all network communications between microservice. It is like having a gateway for every service, with central control.

For conclusion, Istio helps solve the problems on connection between services. But this does not mean Istio solves all the problem. What Istio does is it provide a window for developers to view the complexity which are originally separated in the system. It does not lower the complexity. Moreover, developers even need to maintain Istio itself, normally deploy on Kubernetes, which is both very complex system. If a developer team does not have an experience person which have deep understanding of both Istio and Kubernetes, the cost of implementing Istio might come greater than its benefits.

# Conclusion

There is no silver bullet, with every technology we decide to implement on our application, we must always remember the problem that they are designate to solve. When the cost of implement that technology is larger than the benefits it can provide, or the technology cannot solve the problem in our specific environment, we must give up them and not follow the trend. Microservice + k8s + Istio real hard tho.