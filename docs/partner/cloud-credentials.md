# **Cloud Credentials**

*Select organization* for a better overview of Cloud Credentials.

See all projects for each hosting provider:

* AWS
* Azure
* OpenStack

<figure markdown>
  ![Cloud Credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/cloud-credentials/cc.gif "Cloud Credentials")
  <figcaption>Fig. 1: Cloud Credentials</figcaption>
</figure>

Cloud can be empty but also may include multiple projects. Each Cloud has different specifics, can be sorted differently and some columns can be expanded.

You can expand all tables to see the last modification made (*Created By*, *Last Modified*, *Last Modified By*).

<figure markdown>
  ![Detailed CC for OpenStack](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/cloud-credentials/cc-detailed-openstack.png "Detailed CC")
  <figcaption>Fig. 2: Detailed CC for OpenStack</figcaption>
</figure>

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/make-default.png "Make Default"){: .middle} Make default - choose credentials which will be then filled during project creation, lighter color indicates selected credentials

:pencil2: Update Cloud Credentials - change the credentials which are not locked

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MJQrhtis3vRAM281R7J%2F-MV0tiY8gTU5yO0TIv8s%2F-MV1J1C74Xh5W-bDHwYe%2Fpie%20chart.png?alt=media\&token=c592b976-1cf6-4337-8d68-8cc6dddf291d)Navigate to OpenStack/Azure Quota Charts - Preview the quotas from your cloud

* you can also filter Azure usage quotas by *cpu*, *storage*, *gallery* or *general*


<figure markdown>
  ![OpenStack Quotas](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/cloud-credentials/pie-charts.gif "Pie Charts")
  <figcaption>Fig. 3: OpenStack Quotas</figcaption>
</figure>


![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png "Lock"){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png "Unlock"){: .middle} Un/lock credentials - if you lock the credentials, you can't use them in new Project, edit or delete them

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "Delete"){: .middle} Delete - delete empty and unlocked credentials


## **New Cloud Credentials**

Use ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/cloud-credentials/add-cc-btn.png){: .middle} button to Add Cloud Credentials. Choose which Cloud you want to add and fill in the required data. After you add new Cloud Credentials, you can use the Cloud as storage for your new projects.


## **Requirements for Openstack**

???+ danger
    For a good working OpenStack in Taikun, you have to create image in OpenStack.  Requirement is an Ubuntu 20 image and we recommend using a recent kernel, e.g. a base Ubuntu image with hwe kernel here: [https://repo.itera.io/repository/images/taikun-image.qcow2](https://repo.itera.io/repository/images/taikun-image.qcow2)

    To use the image in Taikun you have to use the tags "taikun" and "ubuntu{number}”. By default Taikun will take image with the latest {number}.

    Command to add an image to openstack:`openstack image create --disk-format qcow2 --container-format bare --public --tag taikun --tag ubuntu20.04 --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-focal-image --file taikun-image.qcow2`


See [Projects - **Create A New Project**](../projects/creating-a-new-project) or [Guidelines - **Add Cloud Credentials**](../../guidelines/add-cloud-credentials).
