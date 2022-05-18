---
tags:
  - Guidelines
  - Cluster Creation
hide:
  - tags
---

# **Creating a Cluster**

[:fontawesome-solid-user-tie:](../../manager/projects/creating-a-new-project/) **Manager**
[:fontawesome-regular-handshake:](../../partner/projects/creating-a-new-project/) **Partner**

If you have connected your cloud, you can create a new project.

1\) Manager/Partner has to create [a new project](../../manager/projects/creating-a-new-project) and [assign](../../manager/projects/#assigned-users) it to a user.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/create-project-assign-user.gif "Add project and assign it to user")
  <figcaption>Fig .1: Add project and assign it to user</figcaption>
</figure>

???+ warning
    Keep in mind you have to add profiles during project creation otherwise you cannot do it later.


2\) Manager/Partner [binds flavors](../../manager/flavor-info/#bind-to-project) needed to the new project.

a) during project creation

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/add-flavor-during-creation.gif "Flavor - project creation")
  <figcaption>Fig .2: Flavor - project creation</figcaption>
</figure>

b) in Flavor Info

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/add-flavor-flavor-info.gif"Flavor - Flavor Info")
  <figcaption>Fig .3: Flavor - Flavor info</figcaption>
</figure>

???+ warning
    For a well-functioning cluster you should **NOT** use small flavors.

3\) Now User/Manager/Partner can create new servers in the project. Keep in mind, that a working cluster consists at least of 1 Bastion, 1 Kubemaster and 1 Kubeworker. However, you can also create a multimaster by creating more than 1 Kubemaster, the number of masters must be odd. If you want to create a multimaster, you have to do it before commit.

???+ info
    Recommendation for sizing:

    * _bastion_ recommended 2 vCPU + 2GB of RAM
    * _masters_ recommended 4 vCPU + 8GB of RAM

* add servers (more info for [User](../../user/projects/project-details-k8s/#add-server), [Manager](../../manager/projects/project-details-k8s/#add-server) and [Partner](../../partner/projects/project-details-k8s/#add-server)

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/add-workers.gif "Add servers")
  <figcaption>Fig .4: Add servers</figcaption>
</figure>

* use shortcuts:
    * b - bastion
    * m - master
    * w - worker
    * numbers of master/worker for faster server addition

???+ info
    The bigger flavor you choose the longer it will take to create.

* commit

???+ warning
    Control if you have all servers you need, the creation can take some time (approx. 7 min per server).

    **User**: Also double check if you need all of them because later you won't be able to delete them.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/commit.gif "Commit")
  <figcaption>Fig .5: Commit</figcaption>
</figure>

* creating the project, servers get through the stages:
    * ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/pending.png){: .middle}:arrow_right:![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/updating.png){: .middle}:arrow_right:![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/ready.png){: .middle}

* successful creation, the project is *Ready*

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/servers-ready.png)
  <figcaption>Fig .6: Ready</figcaption>
</figure>

* failed creation, the project is *Failed* or *Pending* without any action
    * if servers fail during creation, best way to restore them is with **repair** button (details: [User](../../user/projects/project-details-k8s/#repair), [Manager](../../manager/projects/project-details-k8s/#repair), [Partner](../../partner/projects/project-details-k8s/#repair))

* delete servers
    * Manager/Partner can delete unnecessary servers

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/create-cluster/delete-server.gif)
  <figcaption>Fig .7: Delete unnecessary servers</figcaption>
</figure>

???+ info
     You can delete servers to still have working cluster (1 bastion, 1 master and 1 worker) or delete the whole working cluster.


4\) Control remotely.

Use [kubeconfig](../backup-monitoring-lock-reboot/#kubeconfigs) file to connect to your kubernetes.


???+ warning
    Please do NOT deploy any apps in monitoring **Service**, because Taikun uses the monitoring namespace heavily! And if you disable the monitoring, all pvc in monitoring will be deleted.
