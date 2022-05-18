---
tags:
  - User
  - Tables
hide:
  - tags
---

# **Tables**

## **Kubernetes**

The **Kubernetes** chart consists of 3 main sections:

* Project
* Nodes
* Pods

<figure markdown>
  ![Kubernetes](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/kubernetes.gif "Kubernetes")
  <figcaption>Fig .1: Kubernetes</figcaption>
</figure>

**Projects**

In the right corner you can switch between **Projects** with Kubernetes (to which you are assigned to).

**Nodes**

Lists Nodes by *Name* and shows status of *Disk*, *Memory*, *PIDs* and *Ready* (Status of the Node).

![Status: working](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/status-working.png "Status: working"){: .middle} Status: working

![Status: not working](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/status-not-working.png "Status: not working"){: .middle} Status: not wokring

**Pods**

For every **Pod** (characterized by *Pod Name*) is listed its *Namespace*, *Node*, *Restart* *Count*, *Age* and *Status*.

If the status is failed, you can check the pod in Kubernetes section - use the link in *Nodes - Metadata Name* or *Pods - Pod Name*.

<figure markdown>
  ![Node/Pod failure](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/node-pod-failure.gif "Node/Pod Failure")
  <figcaption>Fig .2: Node/Pod failure</figcaption>
</figure>

For more information see [**Projects - Kubernetes**](../projects/kubernetes.md).

## **Project Resource Allocation**

In this section you can see how the usage of *CPUs*, *RAM* and *Disk* *Size* are divided between the individual projects. The last column *Total* shows the sum of all projects for *CPU*, *RAM* or *Disk Size*. You can also sort *CPU*, *RAM* and *Disk Size*  by *Usage* or *Limit* (if there is any).

<figure markdown>
  ![Project Resource Allocation](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/project-resource-allocation.gif "Project Resource Allocation")
  <figcaption>Fig .3: Project resource allocation</figcaption>
</figure>

The pie charts shows percentage of usage of each project:

![Green - small usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/green-small-usage.png "Small Usage"){: .middle} Green - small usage

![Yellow - normal usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/yellow-normal-usage.png "Normal Usage"){: .middle} Yellow - normal usage

![Orange - higher usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/orange-higher-usage.png "Higher Usage"){: .middle} Orange - higher usage

![Red - full usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/red-full-usage.png "Full Usage"){: .middle} Red - full usage

## **Recent Events**

Lists 10 events from the latest. Green ones are successful events, red ones are failed. The update button is in the right corner.

<figure markdown>
  ![Recent Events](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/recent-events.gif "Recent Events")
  <figcaption>Fig .4: Recent events</figcaption>
</figure>

???+ warning
	If there is a real-time change, you are notified through **Notifications** :bell:.

### **Notifications**

#### General
Whenever user makes a change (create project, add backup, delete project etc.) you are notified via bell :bell: at the top of the page.

The colors indicate:

* green - successful action
* red - failed action

<figure markdown>
  ![Notifications - General](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/notifications-general.png "General Notifications")
  <figcaption>Fig .5: Notifications - General</figcaption>
</figure>

#### Alerts
Notifications for projects when alert starts or is resolved (e.g. Kubernetes health status), you are also notified via bell :bell: at the top of the page.

* green - resolved problem
* red - problem

<figure markdown>
  ![Notifications - Alerts](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/tables/notifications-alerts.png "Alerts Notifications")
  <figcaption>Fig .6: Notifications - Alerts</figcaption>
</figure>

The notification contains a brief message on a specific project and bellow the message is time of the change. After clicking **Show Project**, you will access the project in which the change was made.

???+ info
    As the name suggests: *Mark as Read* and *Dismiss all*.
