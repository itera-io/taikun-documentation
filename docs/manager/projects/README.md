---
description: Summary and Details of All Projects
---

# Projects

On the **Projects** tab, you can preview all existing projects for your organization.

![Fig. 1: Projects](<../../.gitbook/assets/projects (5).png>)

Each project is described by following information:

#### Id, Project Name, Organization Name

Changeless descriptions for each Project.

#### Status

Status shows the current status and actions of your servers in the project in real-time. Below are all possible statuses listed with their description.

* Ready
  * all servers in the project are ready without any issues
* Deleting
  * one or more servers in your current project are being deleted
* Failure
  * one or more servers failed during the action for any reason (for instance during boot or creation)
* Pending
  * one or more servers are in a pending state, which means that, for instance, they have not yet been created on the hosted platform
* Updating
  * one or more servers in the project are being updated by Taikun during the creation process
* Upgrading
  * one or more servers upgrade Kubernetes, cloud credentials or others

#### Health

This column describes a condition of the project cluster. Keep in mind that a good-working project should be always **Healthy.**

* Healthy
  * cluster id without any further problems
* None
  * cluster is probably empty, there is nothing to check
* Unhealthy
  * problems with connection to Kubernetes or Monitoring API
* Unknown
  * cannot connect Kubernetes API
* Warning
  * minor issues

&#x20;**Creation Date**

The exact time stamp when the project was created.

#### Kubernetes Version

Shows current Kubernetes version for each project.

#### Cloud Type

Shows which provider is hosting your project cluster

* AWS
* Azure
* OpenStack

#### K8's

![](../../.gitbook/assets/kubernetes-active.png)Kubernates active

![](../../.gitbook/assets/kubernetes-not-active.png)Kubernetes not active

#### Expiration Date

This feature helps you to manage your project - its durability. By default, the expiration date to your project is set to infinity. You can set it during project creation or modify it after the project is created with _Extend Project Lifetime_.

{% hint style="danger" %}
After the expiration date, your project is **NOT** affected, deleted or lock. It will stays the same.
{% endhint %}

#### Assigned Users

![](../../.gitbook/assets/assigned.png)Edit which users should have access to the project, confirm with update button

{% hint style="info" %}
You can also assign the user to a project in [Users](https://itera.gitbook.io/taikun/user-guide-1/manager/users).
{% endhint %}

#### Actions

![](<../../.gitbook/assets/lock (3).png>)Lock Project - disable all buttons which can cause some changes in project (see [Projects - **Project Details**](https://itera.gitbook.io/taikun/manager/projects/project-details#lock-unlock))

![](../../.gitbook/assets/unlock.png)Unlock Project - enable action buttons

![](<../../.gitbook/assets/delete (2).png>)Delete - to delete project, the project must be empty with status _Ready_





#### Show hidden columns

Click small arrow on the right side of the table to see more details.

![Fig. 2: Expanded table](<../../.gitbook/assets/projects-expand (2).png>)

Expand the table to see:

* Alerts count - number of firing alerts in a project
* Created By
* Last Modified
* Last Modified By



#### Sorting

Projects can be sorted by _Project Name, Organization Name_, _Status_, _Creation Date_, _Kubernetes version_ or _Cloud Type_. Also the search bar can be used to find some specific project.
