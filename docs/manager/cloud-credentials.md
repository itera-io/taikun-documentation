# **Cloud Credentials**

See all projects for each hosting provider:

* AWS
* Azure
* OpenStack

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/cloud-credentials/cc.gif "Cloud Credentials")
  <figcaption>Figure.1: Cloud credentials</figcaption>
</figure>

Cloud can be empty but also may include multiple projects. Each Cloud has different specifics, can be sorted differently and some columns can be expanded.

You can expand all tables to see the last modification made (*Created By*, *Last Modified*, *Last Modified By*).

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/cloud-credentials/cc.png "Detailed CC for OpenStack")
  <figcaption>Figure.2: Detailed CC for openstack</figcaption>
</figure>

## **Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/make-default.png){: .middle} Make default - choose credentials which will be then filled during project creation, lighter color indicates selected credentials

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/edit.png){: .middle} Update Cloud Credentials - change the credentials which are not locked

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/pie-charts.png){: .middle} Navigate to OpenStack/Azure Quota Charts - Preview the quotas from your cloud

* you can also filter Azure usage quotas by *cpu*, *storage*, *gallery* or *general*

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/cloud-credentials/pie-charts.gif "OpenStack/Azure Quotas")
  <figcaption>Figure.3: OpenStack/Azure Quotas</figcaption>
</figure>

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Un/lock credentials - if you lock the credentials, you can't use them for new Project, edit or delete them

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete - delete empty and unlocked credentials

## **New Cloud Credentials**

Use![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/cloud-credentials/add-cc-btn.png){: .middle} button to add Cloud Credentials. Choose which Cloud you want to add and fill in the required data. After you add new Cloud Credentials, you can use the Cloud as storage for your new projects.

### **Requirements for OpenStack**

???+ warning

    For a good working OpenStack in Taikun, you have to create image in OpenStack. Requirement is an Ubuntu 20 image and we recommend using a recent kernel, e.g. a base Ubuntu image with hwe kernel here: [https://repo.itera.io/repository/images/taikun-image.qcow2](https://repo.itera.io/repository/images/taikun-image.qcow2)

    To use the image in Taikun you have to use two **tags** "taikun" and "ubuntu{number}”. By default Taikun will take image with the latest {number}.

    Command to add an image to openstack:

    `openstack image create --disk-format qcow2 --container-format bare --public --tag taikun --tag ubuntu20.04 --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-focal-image --file taikun-image.qcow2`

See [**Projects - Create A New Project**](../projects/creating-a-new-project) or [**Guidelines - Add Cloud Credentials**](../../guidelines/create-credentials).
