# **Tables**

## **Kubernetes**

The **Kubernetes** chart consists of 3 main sections:

* Project
* Nodes
* Pods

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/kubernetes.gif "Kubernetes")
  <figcaption>Fig .1: Kubernetes</figcaption>
</figure>

**Projects**

In the right corner you can switch between **Projects** with Kubernetes (for your organization).

**Nodes**

Lists Nodes by *Name* and shows status of *Disk*, *Memory*, *PIDs* and *Ready* (Status of the Node).

![Status: working](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/status-working.png"Status: working"){: .middle} Status: working

![Status: not working](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/status-not-working.png){: .middle} Status: not wokring

**Pods**

For every **Pod** (characterized by *Pod Name*) is listed its *Namespace*, *Node*, *Restart* *Count*, *Age* and *Status*.

If the status is failed, you can check the pod in Kubernetes section - use the link in *Nodes - Metadata Name* or *Pods - Pod Name*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/node-pod-failure.gif "Node/Pod failure")
  <figcaption>Fig .2: Node/Pod failure</figcaption>
</figure>

For more information see [**Projects - Kubernetes**](../../projects/kubernetes).

## **Project Resource Allocation**

In this section you can see how the usage of *CPUs*, *RAM* and *Disk* *Size* are divided between the individual projects. The last column *Total* shows the sum of all projects for *CPU*, *RAM* or *Disk Size*. You can also sort *CPU*, *RAM* and *Disk Size*  by *Usage* or *Limit* (if there is any).

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/project-resource-allocation.gif "Project Resource Allocation")
  <figcaption>Fig .3: Project resource allocation</figcaption>
</figure>

The pie charts shows percentage of usage of each project:

![Green - small usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/green-small-usage.png "Small Usage"){: .middle} Green - small usage

![Yellow - normal usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/yellow-normal-usage.png "Normal Usage"){: .middle} Yellow - normal usage

![Orange - higher usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/orange-higher-usage.png "Higher Usage"){: .middle} Orange - higher usage

![Red - full usage](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/red-full-usage.png "Full Usage"){: .middle} Red - full usage

Limits can be changed in [**Project Quotas**](../../project-quotas).

## **Recent Events**

Lists 10 events from the latest. Green ones are successful events, red ones are failed. The update button is in the right corner.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/recent-events.gif "Recent Events")
  <figcaption>Fig .4: Recent events</figcaption>
</figure>

By clicking *Show all* you are redirected to [**Audit Log**](../../audit-log).

???+ warning
    If there is a real-time change, you are notified through **Notifications** :bell:.
