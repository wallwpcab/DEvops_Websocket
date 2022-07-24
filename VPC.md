
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
