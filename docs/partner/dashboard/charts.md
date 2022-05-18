---
tags:
  - Partner
  - Charts
hide:
  - tags
---

# **Charts**

## **Projects**

The graph shows number of **Projects** (right corner) for your organization and the pie chart shows their current status (pointing arrow at some part of the graph):

* Failed
* Succeeded
* Pending
* Updating

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/projects.gif "Projects")
  <figcaption>Fig. 1: Projects</figcaption>
</figure>

By clicking the specific part in graph, you see an overview of selected projects.

For more information visit [**Projects**](../../projects).

## **Server Statuses**

In the right corner is number of **Servers** and the pie chart shows their current status (pointing arrow at some part of the graph):

* Failed
* Succeeded
* Pending
* Updating

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/server-statuses.gif "Server Statuses")
  <figcaption>Fig. 2: Server Statuses</figcaption>
</figure>

By clicking the specific part in graph you see an overview of selected servers.

For more information visit [**Servers**](../../servers).

## **Servers**

In the right corner is shown number of all **Servers** for your organization. The graph shows where the servers are hosted (*AWS*, *Azure*, *OpenStack*). When you point at a column, exact number of servers used is shown.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/servers.gif "Servers")
  <figcaption>Fig. 3: Servers</figcaption>
</figure>

For more information about servers visit [**Servers**](../../servers), for clouds visit [**Cloud Credentials**](../../cloud-credentials).

## **Cloud Credentials**

In the right corner is shown number of **Cloud Credentials**. The graph shows which cloud (*AWS*, *Azure*, *OpenStack*) and how many of each type are used. When you point to a column, the exact number of cloud credentials used is shown. In the right corner is number of all cloud credentials.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/cloud-credentials.gif "Cloud Credentials")
  <figcaption>Fig. 4: Cloud Credentials</figcaption>
</figure>

For more information visit [**Cloud Credentials**](../../cloud-credentials).

## **Nodes overview**

In the right corner is shown number of **Nodes** and the pie chart shows their current status (pointing arrow at some part of the graph):

* Healthy
* Unhealthy

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/nodes-overview.gif "Nodes Overview")
  <figcaption>Fig. 5: Nodes overview</figcaption>
</figure>

By clicking the graph you see [Kubernetes](../../projects/kubernetes) overview, where you can find Projects with number of Healthy and Unhealthy Nodes.


## **Pods overview**

In the right corner is shown number of [**Pods**](../../projects/kubernetes#pods) and the pie chart shows their current status (pointing arrow at some part of the graph):

* Healthy
* Unhealthy

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/pods-verview.gif "Pods Overview")
  <figcaption>Fig. 6: Pods overview</figcaption>
</figure>

By clicking the graph you see [Kubernetes](./../projects/kubernetes) overview, where you can find Projects with number of Healthy and Unhealthy Pods.

## **Projects with Alerts**

In the right corner is shown number of all **alerts** and the pie chart shows how many alerts has each project (pointing arrow at some part of the graph):

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/projects-with-alerts.gif "Projects with alerts")
  <figcaption>Fig. 7: Projects with Alerts</figcaption>
</figure>

By clicking the graph you see Kubernetes overview, where you can find Projects with number of alerts.

For more information see [Projects - **Alerts**](../../projects/project-details#alerts).

## **Kubernetes Health**

In the right corner is shown number of **Non-Healthy** items  and the pie chart shows status for all projects with active kubernetes (pointing arrow at some part of the graph):

* Healthy
* Unhealthy
* Warning
* Unknown

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/kubernetes-health.gif "Kubernetes Health")
  <figcaption>Fig. 8: Kubernetes Health</figcaption>
</figure>

By clicking the graph you see Kubernetes overview, where you can find Projects (with kubernetes) with its kubernetes health status.

For more information see [**Projects- Health**](../../projects/#health).

##  **Open Project**

By clicking the specific part in graph, you see an overview of selected projects. Use![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/dashboard/charts/open-project.png "Open Project"){: .middle} to access the project. Works for every graph except *Servers* and *Cloud Credentials*.
