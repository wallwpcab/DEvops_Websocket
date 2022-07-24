
VPC overview

Virtual Private Cloud (VPC) provides networking functionality to Compute Engine virtual machine (VM) instances, Google Kubernetes Engine (GKE) clusters, and the App Engine flexible environment. VPC provides networking for your cloud-based resources and services that is global, scalable, and flexible.

This page provides a high-level overview of VPC concepts and features.


VPC networks

You can think of a VPC network the same way you'd think of a physical network, except that it is virtualized within Google Cloud. A VPC network is a global resource that consists of a list of regional virtual subnetworks (subnets) in data centers, all connected by a global wide area network. VPC networks are logically isolated from each other in Google Cloud.
VPC network example (click to enlarge)
VPC network example (click to enlarge)

A VPC network provides the following:

    Provides connectivity for your Compute Engine virtual machine (VM) instances, including Google Kubernetes Engine (GKE)      clusters, App Engine flexible environment instances, and other Google Cloud products built on Compute Engine VMs.
    Offers built-in Internal TCP/UDP Load Balancing and proxy systems for Internal HTTP(S) Load Balancing.
    Connects to on-premises networks using Cloud VPN tunnels and Cloud Interconnect attachments.
    Distributes traffic from Google Cloud external load balancers to backends.

Read more about VPC networks.


Firewall rules

Each VPC network implements a distributed virtual firewall that you can configure. Firewall rules allow you to control which packets are allowed to travel to which destinations. Every VPC network has two implied firewall rules that block all incoming connections and allow all outgoing connections.

The default network has additional firewall rules, including the default-allow-internal rule, which permit communication among instances in the network.

Read more about firewall rules.



Routes

Routes tell VM instances and the VPC network how to send traffic from an instance to a destination, either inside the network or outside of Google Cloud. Each VPC network comes with some system-generated routes to route traffic among its subnets and send traffic from eligible instances to the internet.

You can create custom static routes to direct some packets to specific destinations.

Read more about routes.
Forwarding rules

While routes govern traffic leaving an instance, forwarding rules direct traffic to a Google Cloud resource in a VPC network based on IP address, protocol, and port.

Some forwarding rules direct traffic from outside of Google Cloud to a destination in the network; others direct traffic from inside the network. Destinations for forwarding rules are target instances, load balancer targets (target proxies, target pools, and backend services), and Cloud VPN gateways.

Read more about forwarding rules.
Interfaces and IP addresses
IP addresses

Google Cloud resources, such as Compute Engine VM instances, forwarding rules, GKE containers, and App Engine, rely on IP addresses to communicate.

Read more about IP addresses.
Alias IP ranges

If you have multiple services running on a single VM instance, you can give each service a different internal IP address by using alias IP ranges. The VPC network forwards packets that are destined to a particular service to the corresponding VM.

Read more about alias IP ranges.
Multiple network interfaces

You can add multiple network interfaces to a VM instance, where each interface resides in a unique VPC network. Multiple network interfaces enable a network appliance VM to act as a gateway for securing traffic among different VPC networks or to and from the internet.

Read more about multiple network interfaces.
VPC sharing and peering
Shared VPC

You can share a VPC network from one project (called a host project) to other projects in your Google Cloud organization. You can grant access to entire Shared VPC networks or select subnets therein by using specific IAM permissions. This lets you provide centralized control over a common network while maintaining organizational flexibility. Shared VPC is especially useful in large organizations.

Read more about Shared VPC.
VPC Network Peering

VPC Network Peering lets you build software as a service (SaaS) ecosystems in Google Cloud, making services available privately across different VPC networks, whether the networks are in the same project, different projects, or projects in different organizations.

With VPC Network Peering, all communication happens by using internal IP addresses. Subject to firewall rules, VM instances in each peered network can communicate with one another without using external IP addresses.

Peered networks automatically exchange subnet routes for private IP address ranges. VPC Network Peering lets you configure whether the following types of routes are exchanged:

    Subnet routes for privately re-used public IP ranges
    Custom static and dynamic routes

Network administration for each peered network is unchanged: IAM policies are never exchanged by VPC Network Peering. For example, Network and Security Admins for one VPC network do not automatically get those roles for the peered network.

Read more about VPC Network Peering.
Hybrid cloud
Cloud VPN

Cloud VPN lets you connect your VPC network to your physical, on-premises network or another cloud provider by using a secure virtual private network.

Read more about Cloud VPN.
Cloud Interconnect

Cloud Interconnect lets you connect your VPC network to your on-premises network by using a high speed physical connection.

Read more about Cloud Interconnect.
Cloud Load Balancing

Google Cloud offers the following load balancing configurations to distribute traffic and workloads across many VMs:

    Global external load balancing, including HTTP(S) Load Balancing, SSL Proxy Load Balancing, and TCP Proxy Load Balancing
    Regional external Network Load Balancing
    Regional Internal TCP/UDP Load Balancing

Read more about Cloud Load Balancing.
Special configurations
Private Google Access

When you enable Private Google Access for a subnet, instances in a subnet of a VPC network can communicate with Google APIs and services by using private IP addresses instead of external IP addresses.

Read more about Private Google Access.







