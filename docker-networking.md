## Docker Networking



Watch this YouTube video: [Docker networking is CRAZY!! (you NEED to learn it) (youtube.com)](https://www.youtube.com/watch?v=bKFMS5C4CG0)



---



### Networking Overview

Excerpt from [Networking overview | Docker Docs](https://docs.docker.com/network/)

>Container networking refers to the ability for containers to connect to and communicate with each other, or to non-Docker workloads.
>
>Containers have networking enabled by default, and they can make outgoing connections. A container has no information about what kind of network it's attached to, or whether their peers are also Docker workloads or not. A container only sees a network interface with an IP address, a gateway, a routing table, DNS services, and other networking details. That is, unless the container uses the `none` network driver.



---



### Default Bridge Network

>When Docker Engine on Linux starts for the first time, it has a single built-in network called the "default bridge" network. When you run a container without the --network option, it is connected to the default bridge.
>
>Containers attached to the default bridge have access to network services outside the Docker host. They use "masquerading" which means, if the Docker host has Internet access, no additional configuration is needed for the container to have Internet access.



---



### User-defined Bridge Networks

>It can be useful to separate groups of containers that should have full access to each other, but restricted access to containers in other groups.
>
>You can create custom, user-defined networks, and connect groups of containers to the same network. Once connected to a user-defined network, containers can communicate with each other using container IP addresses or container names.

Run the examples on [User-defined bridge networks | Docker Docs](https://docs.docker.com/engine/network/#user-defined-networks)

![user-defined-bridge](./docker-networking.assets/user-defined-bridge.webp) 

 

Topology of user-defined bridge networks demo.



---



### Host Network

>If you use the host network mode for a container, that container's network stack isn't isolated from the Docker host (the container shares the host's networking namespace), and the container doesn't get its own IP-address allocated. For instance, if you run a container which binds to port 80 and you use host networking, the container's application is available on port 80 on the host's IP address.

Run the examples on [Host network driver | Docker Docs](https://docs.docker.com/engine/network/drivers/host/)

