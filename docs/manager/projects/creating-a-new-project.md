# **Create a New Project**

If you want to add a new project, use the upper right button![]( https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/create-project/add-project-btn.png "add-project"){: .middle}in **Projects** tab.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/create-project/add-project.gif "Add Project")
  <figcaption>Figure.1: Add project</figcaption>
</figure>

**Project Name** - fill in your project name (only alphanumeric lowercase characters and dash are allowed, 3-30 characters; **not** underscore; e.g. my-project1)

**Cloud** - choose where you want to store your Project, create a new Cloud in [**Cloud Credentials**](../../cloud-credentials)

**Access Profile** - choose profile which can access the project, create a new profile in [**Access Profiles**](../../access-profiles)

**Alerting Profile** - if you have created profile in [**Alerting Profiles**](../../alerting-profiles), you can choose it from the drop-down selection

**Kubernetes Profile** - first create a new profile in [**Kubernetes Profiles**](../../kubernetes-profiles) and than choose from drop down selection

* for openstack: if you choose profile with enabled Taikun Load Balancer, you also have to fill in *Taikun Load Balancer Flavor*, *Router Id Start Range* and *Router Id End Range*

**Enable Auto Upgrade** - Kubespray version will be automatically upgraded if new version is available

**Enable Monitoring** - monitoring a Kubernetes cluster allows easy management of containerized infrastructure by tracking utilization of cluster resources including memory, CPU, and storage

**Enable Backup** - choose credentials, you can create a new one in [**Backup Credentials**](../../backup-credentials)**.** If you choose not to enable it, you can change it later, see [**Projects - Project details - Backup**](../project-details#enable-disable-backup)

**Add Policy Profile** - select a policy profile for the project

**Add Expiration Date** - set project durability, by default it is set to infinity. After the expiration date, your project is **NOT** affected, deleted or lock. It will stays the same.

**Enable Spot** - enable spots

* **Allow Spot VM’s** - allow spots in standalone VMs
* **Allow Full Spot Kubernetes** - allow full spot on kubernetes
* **Allow Spot Workers** - allow spot on workers
* **No Spot for Kubernetes**

**Specify Kubernetes Version** - select the kubernetes version for the project

**Add Flavor** - bind the flavor to the project, you can bind more than one flavor and un/bind them later in [**Flavor Info**](../flavor-info)
