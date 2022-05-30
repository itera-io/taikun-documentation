# Projects

On the **Projects** tab, you can preview all existing projects for your organization.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/projects.png "Projects")
  <figcaption>Figure.1: Projects</figcaption>
</figure>

*Select organization* - choose organization to see all projects for your selection

Each project is described by the following information:

### **Id, Project Name, Organization Name**

Changeless descriptions for each Project.

### **Status**

Status shows the current status and actions of your servers in the project in real-time. Below are all possible statuses listed with their description.

* *Ready*
    * all servers in the project are ready without any issues
* *Deleting*
    * one or more servers in your current project are being deleted
* *Failure*
    * one or more servers failed during the action for any reason (for instance during boot or creation)
* *Pending*
    * one or more servers are in a pending state, which means that, for instance, they have not yet been created on the hosted platform
* *Updating*
    * one or more servers in the project are being updated by Taikun during the creation process
* *Upgrading*
    * one or more servers upgrade Kubernetes, cloud credentials or others

### **Health**

This column describes a condition of the project cluster. Keep in mind that a good-working project should be always **Healthy.**

* *Healthy*
    * cluster id without any further problems
* *None*
    * cluster is probably empty, there is nothing to check
* *Unhealthy*
    * problems with connection to Kubernetes or Monitoring API
* *Unknown*
    * cannot connect Kubernetes API
* *Warning*
    * minor issues

### **Creation Date**

The exact time stamp when the project was created.

### **Kubernetes Version**

Shows current Kubernetes version for each project.

#### **Cloud Type**

Shows which provider is hosting your project cluster:

* AWS
* Azure
* OpenStack

### **K8's**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/kubernetes-active.png "Kubernetes active") Kubernates active

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/kubernetes-not-active.png "Kubernetes not active") Kubernetes not active

### **Expiration Date**

This feature helps you to manage your project - its durability. By default, the expiration date to your project is set to infinity. You can set it during project creation or modify it after the project is created with _Extend Project Lifetime_.

???+ warning
    After the expiration date, your project is **NOT** affected, deleted or lock. It will stays the same.

### **Assigned Users**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/assigned.png "Assigned") Edit which users should have access to the project, confirm with update button

???+ info
    You can also assign the user to a project in [Users](../users).

### **Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png "lock"){: .middle} Lock Project - disable all buttons which can cause some changes in project 
(see [**Projects - Project Details**](project-details-k8s#lock-unlock))

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png "unlock"){: .middle} Unlock Project - enable action buttons

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "delete"){: .middle} Delete - to delete project, the project must be empty with status *Ready*

### **Show hidden columns**

Click small arrow on the right side of the table to see more details.

<figure markdown>
  ![]( https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/projects-expand.png "Expanded table")
  <figcaption>Figure.2: Expanded table</figcaption>
</figure>

Expand the table to see:

* Alerts count - number of firing alerts in a project
* Created By
* Last Modified
* Last Modified By

### **Sorting**

Projects can be sorted by *Project Name, Organization Name*, *Status*, *Creation Date*, *Kubernetes version* or *Cloud Type*. Also the search bar can be used to find some specific project.
