---
tags:
  - Manager
hide:
  - tags
---

# Dashboard

You can access the Dashboard by clicking upper left Taikun logo or the **Dashboard** in the tabs (under User):

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/accessing-dashboard.gif "Accessing Dashboard")
  <figcaption>Fig .1: Dashboard</figcaption>
</figure>

On Dashboard you can find:

* [**Users**](users/)
* [**Pie charts**](charts/) (Projects, Server Statuses, Servers, Cloud Credential, Nodes Overview, Pod overview, Project with Alerts and Kubernetes Health)
* [**Tables**](tables/) (Kubernetes, Project Resource Allocation and Recent Events)

## **Header**

On every page in the upper right corner you can see:

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/icons-upper-right.png "Icons upper right")
  <figcaption>Fig .2: Header icons</figcaption>
</figure>

![Logo of Organization](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/logo.png "Logo if your Organization")

* logo of your organization

![Docs](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/docs.png "Docs")

* link to this documentation, variable for every page

![Search](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/global-search.png "Search")

* global search - search for projects or servers, case insensitive, can be open with *double shift* at every page
    * Taikun search - search through projects, users, servers, credentials or profiles
    * Kubernetes Search - have to be checked (as searching kubernetes takes longer time) and search through all active kubernetes

![Notifications](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/bell.png "Notifications")

* real-time notifications
    * General - notifications about changes made in projects (e.g. created project, enable monitoring, change of status), for details see [**Dashboard - Recent Events**](tables#recent-events)    

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/notifications-general.png "General Notifications")
  <figcaption>Fig .3: General notifications</figcaption>
</figure>

    * Alerts - new/persisting (red) or resolved (green) alerts, see [**Projects - Alerts**](../projects/project-details#alerts)    

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/notifications-alerts.png "Alert notifications")
  <figcaption>Fig .4: Notifications alerts</figcaption>
</figure>

    * Tickets - you will be notified when your ticket has been commented or change the status, for details see [**Ticketing**](../ticketing/)    

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/tables/notifications-tickets.png "Ticketing notifications")
  <figcaption>Fig .5: Notifications tickets</figcaption>
</figure>

![My Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/my-profile.png "My Profile")

* your information and setting, see [**My Profile**](../my-profile/)
* if your display name is changed, the name can be seen in the corner![My Profile - manager](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/my profile-name.png "My Profile - manager"){: .middle}
