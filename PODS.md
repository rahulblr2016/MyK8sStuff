# PODS



PODS are the atom of Kubernetes cluster. In Kubernetes instead of deploying the containers individually, we deploy Pods. *Pods* are the smallest deployable units of computing that you can create and manage in Kubernetes.

Why POD?  
The answer is quite simple. For an application user, the container is kind of Virtual Machine, the end user can login, install some packages, stop/start it, so it behaves like an VM to the end user. Also, the containers are designed to run a single process per container. What is an Application requires multiple processes that communicate via IPC or through local files, so in that case they need to run on the same machine(or VM). 
As mentioned grouping multiple processes in a single container is NOT the best practice, so what the solution is ?? This is where PODs comes into the picture.  So, POD 

- POD can have one or more containers running inside it (It doesn't mean that you have to always run multiple containers inside the POD). POD allows you to run closely related process together and provide them same environment. 
- Containers in a pod have shared volumes, Linux namespaces, and cgroups. Each pod has a unique IP address and the port space is shared by all the containers in that pod. This means that different containers inside a pod can communicate with each other using their corresponding ports on localhost
- POD always run on a single worker node,it never spans across multiple worker nodes.
- Containers running inside the POD share the same Network Namespace (Linux) i.e. they share the same IP address, same loopback NIC and PORT space.
- All PODs in a K8s cluster (irrespective of the worker nodes ), resides in a single flat shared Network space, i.e. every Pod can access every Pod with its IP address, no NATING is require, it is just like they are connected over same LAN.

![img](https://cdn-images-1.medium.com/max/1200/1*6U9j1CeOvjNjit6eUEZgNA.png)





