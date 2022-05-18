---
tags:
  - User
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
  ![Projects](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/projects.gif "Projects")
  <figcaption>Fig .1: Projects</figcaption>
</figure>

By clicking the specific part in graph, you see an overview of selected projects.

For more information visit [**Projects**](../../projects/).

## **Server Statuses**

In the right corner is number of **Servers** and the pie chart shows their current status (pointing arrow at some part of the graph):

* Failed
* Succeeded
* Pending
* Updating

<figure markdown>
  ![Server Statuses](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/server-statuses.gif "Server Statuses")
  <figcaption>Fig .2: Server statuses</figcaption>
</figure>

By clicking the specific part in graph you see an overview of selected servers.

## **Servers**

In the right corner is shown number of all **Servers** for your organization. The graph shows where the servers are hosted (*AWS*, *Azure*, *OpenStack*). When you point at a column, exact number of servers used is shown.

<figure markdown>
  ![Servers](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/servers.gif "Servers")
  <figcaption>Fig .3: Servers</figcaption>
</figure>

## **Cloud Credentials**

In the right corner is shown number of **Cloud Credentials**. The graph shows which cloud (*AWS*, *Azure*, *OpenStack*) and how many of each type are used. When you point to a column, the exact number of cloud credentials used is shown. In the right corner is number of all cloud credentials.

<figure markdown>
  ![Ciloud Credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/cloud-credentials.gif "Cloud Credentials")
  <figcaption>Fig .4: Cloud credentials</figcaption>
</figure>

## **Nodes overview**

In the right corner is shown number of **Nodes** and the pie chart shows their current status (pointing arrow at some part of the graph):

* Healthy
* Unhealthy

<figure markdown>
  ![Nodes Overview](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/nodes-overview.gif "Nodes Overview")
  <figcaption>Fig .5: Nodes overview</figcaption>
</figure>

By clicking the graph you see [Kubernetes](../../projects/kubernetes) overview, where you can find Projects with number of Healthy and Unhealthy Nodes.

## **Pods overview**

In the right corner is shown number of [**Pods**](../../projects/kubernetes#pods) and the pie chart shows their current status (pointing arrow at some part of the graph):

* Healthy
* Unhealthy

<figure markdown>
  ![Pods Overview](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/pods-overview.gif "Pods Overview")
  <figcaption>Fig .6: Pods overview</figcaption>
</figure>

By clicking the graph you see [Kubernetes](../../projects/kubernetes) overview, where you can find Projects with number of Healthy and Unhealthy Pods.

## **Projects with Alerts**

In the right corner is shown number of all **alerts** and the pie chart shows how many alerts has each project (pointing arrow at some part of the graph):

<figure markdown>
  ![Projects with Alerts](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/projects-with-alerts.gif "Projects with Alerts")
  <figcaption>Fig .7: Project with alerts</figcaption>
</figure>

By clicking the graph you see Kubernetes overview, where you can find Projects with number of alerts.

For more information see [**Projects - Alerts**](../../projects/project-details-k8s#alerts).

## **Kubernetes Health**

In the right corner is shown number of **Non-Healthy** items and the pie chart shows status for all projects with active kubernetes (pointing arrow at some part of the graph):

* Healthy
* Unhealthy
* Warning
* Unknown

<figure markdown>
  ![Kubernetes Health](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/Dashboard/charts/kubernetes-health.gif "Kubernetes Health")
  <figcaption>Fig .8: Kubernetes health</figcaption>
</figure>

By clicking the graph you see Kubernetes overview, where you can find Projects (with kubernetes) with its kubernetes health status.

For more information see [**Projects- Health**](../../projects/#health).
