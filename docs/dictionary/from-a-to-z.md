---
description: Taikun frequently used words explained
---

# From A to Z

**Access Profile** - a profile using http proxy, ssh (we support RSA, ECDSA or Ed25519), dns or ntp to access your _cluster_, the condition is that you add it to the _project_ during creation.

**Alerting Profile** - a profile attached to _project_ gives you notifications about alerts in your _project_.

**Audit Log** - summary of changes made in _projects_.

**Backup credentials** - Taikun is uses AWS S3 backup. S3 (Simple Storage Service) Backup is a desktop application using Amazon’s infrastructure for remote backups and secure online file storage. It features very strong encryption, compression, easy access to your backed up files and backup scheduling built in.

**Backup policy** - defines the ground rules for planning, executing and validating backups and includes specific activities to ensure that critical data is backed up to secure storage media located in a secure location.

* schedules=policies
* backups=a copy created based on policy
* restores=a copy from backup data

**Billing Rules** - rules for C_hargeback_. Every rule is based on external source, metrics and price.

**Chargeback** - external billing set by _Billing Rules_, you can see the price for every _rule_ for selected time period.

**Cloud** - a global network of servers, each with a unique function. These servers are designed to either store and manage data, run applications, or deliver content or a service such as streaming videos, web mail, office productivity software, or social media. Cloud operates as a single ecosystem.

* Taikun is now supporting OpenStack, AWS, Azure and we are planning to support GCP as well.

**Cluster** = project - a set of computers hat work together so that they can be viewed as a single system

* **Kubernetes cluster** - a set of nodes that run containerized applications. Containerizing applications packages an app with its dependencies and some necessary services. They are more lightweight and flexible than virtual machines. In this way, Kubernetes clusters allow for applications to be more easily developed, moved and managed.&#x20;

**CNI** - Container Network Interface, consists of a specification and libraries for writing plugins to configure network interfaces in Linux containers, along with a number of supported plugins. [CNI](https://github.com/containernetworking/cni)

**Credentials** - data confirming the identity of the user or external application (e.g. the user name and password, user name and API key, or authentication token that the identity service provide). In Taikun you can find Cloud Credentials, Backup Credentials, Billing Credentials and Showback Credentials.

**CSM** - Customer Success Manager

**Endpoint** - a remote computing device that communicates back and forth with a network to which it is connected (usually URL address).

**Flavor** - is an available hardware configuration for a server. Defines the compute, memory, and storage capacity of nova computing instances

**Floating IP** - a kind of virtual IP address that can be dynamically routed to any server in the same network. Multiple servers can own the same Floating IP address, but it can only be active on one server at any given time.

**Import network** - use the network already created in cloud (works for OpenStack)

**Keycloak** - an open source software product to allow single sign-on with Identity and Access Management aimed at modern applications and services. [Keycloak](https://www.keycloak.org)

**Kubeconfig file** - a file used to configure access to Kubernetes when used in conjunction with the kubectl commandline tool (or other clients). [Kubeconfig](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)

**Kubernetes** - a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. [Kubernetes](https://kubernetes.io)&#x20;

**Kubernetes Profile** - a profile for enabling _kubernetes_ function and features (such as _Octavia_, _Load Balancer_ or _Proxy on bastion_)

**Load Balancer** -  refers to the process of distributing a set of tasks over a set of resources (computing units), with the aim of making their overall processing more efficient. Load balancing can optimize the response time and avoid unevenly overloading some compute nodes while other compute nodes are left idle.

**Metrics** - measure specific characteristics in a countable manner. Metrics are used in _monitoring_ and _billing_.

**Monitoring** - is the process to gather metrics about the operations, to ensure everything functions as expected to support applications and services. By enabling monitoring you can see Logs, Alerts or Metrics.

**Node** - a worker machine in _Kubernetes_ and may be either a virtual or a physical machine, depending on the _cluster_. [Nodes](https://kubernetes.io/docs/concepts/architecture/nodes/)

**Octavia** - exposes the Service externally using the load balancers from OpenStack.

**Pod** - the smallest execution unit in _Kubernetes_. A pod encapsulates one or more applications. [Pods](https://kubernetes.io/docs/concepts/workloads/pods/)

**Project** = cluster - a set of computers hat work together so that they can be viewed as a single system

* **Kubernetes cluster** - a set of nodes that run containerized applications. Containerizing applications packages an app with its dependences and some necessary services. They are more lightweight and flexible than virtual machines. In this way, Kubernetes clusters allow for applications to be more easily developed, moved and managed.&#x20;

**Proxy on Bastion** - exposes the Service on each Node's IP at a static port, the NodePort. You'll be able to contact the NodePort Service, from outside the cluster, by requesting \<NodeIP>:\<NodePort>.

**Reboot** - to reload the operating system of a computer: to start it up again.

* HARD - the power to the system is physically turned off and back again causing an initial boot
* SOFT - system restarts without the need to interrupt the power

**Role** - defines the rights and permissions granted to user accounts. In Taikun there are _User_, _Manager_ (Owner) or _Partner_. You can take a look at each role in [User Guide](https://itera.gitbook.io/taikun/user).

**Showback** - internal billing set by _Showback Rules_, you can see the price for every _rule_ for selected time period. You can also set external source for billing.

**Showback Rules** - rules for _Showback_. Every rule is based on metrics and price.

**Subscription** - an amount of money that you pay regularly to use Taikun. Price is various depending on the number of users, projects or TCU.

**Token** - an alphanumeric text string that provides access to APIs and resources.

**User** - digital representation of a person using Taikun. Each user is defined by username (e-mail) and the access is granted by _token_. User has assigned _role_ with its permissions.

**Webhook** - way web applications can communicate with each other, allows you to send real-time data from one application to another whenever a given event occurs.
