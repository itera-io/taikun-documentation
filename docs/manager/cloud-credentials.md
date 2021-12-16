---
description: Add, Update, Lock/Unlock or Delete Clouds
---

# Cloud Credentials

See all projects for each hosting provider:

* AWS
* Azure
* OpenStack

![Fig. 1: Cloud Credentials](<../.gitbook/assets/cc (3).gif>)

Cloud can be empty but also may include multiple projects. Each Cloud has different specifics, can be sorted differently and some columns can be expanded.

You can expand all tables to see the last modification made (_Created By_, _Last Modified_, _Last Modified By_).

![Fig. 2: Detailed CC for OpenStack](<../.gitbook/assets/cc (1).png>)

### Actions

![](<../.gitbook/assets/make default.png>)Make default - choose credentials which will be then filled during project creation, lighter color indicates selected credentials

:pencil2: Update Cloud Credentials - change the credentials which are not locked

&#x20;![](<../.gitbook/assets/pie chart.png>)Navigate to OpenStack/Azure Quota Charts - Preview the quotas from your cloud

* you can also filter Azure usage quotas by _cpu_, _storage_, _gallery_ or _general_

![Fig. 3: OpenStack Quotas](<../.gitbook/assets/pie charts (3).gif>)

![](<../.gitbook/assets/lock (3).png>)/![](../.gitbook/assets/unlock.png) Un/lock credentials - if you lock the credentials, you can't use them for new Project, edit or delete them

![](<../.gitbook/assets/delete (2).png>) Delete - delete empty and unlocked credentials



### New Cloud Credentials

Use![](<../.gitbook/assets/add (3).png>)button to add Cloud Credentials. Choose which Cloud you want to add and fill in the required data. After you add new Cloud Credentials, you can use the Cloud as storage for your new projects.



### Requirements for OpenStack

{% hint style="danger" %}
For a good working OpenStack in Taikun, you have to create image in OpenStack. Requirement is an Ubuntu 20 image and we recommend using a recent kernel, e.g. a base Ubuntu image with hwe kernel here: [https://repo.itera.io/repository/images/taikun-image.qcow2](https://repo.itera.io/repository/images/taikun-image.qcow2)

To use the image in Taikun you have to use two **tags** "taikun" and "ubuntu{number}”. By default Taikun will take image with the latest {number}.

Command to add an image to openstack:

`openstack image create --disk-format qcow2 --container-format bare --public --tag taikun --tag ubuntu20.04 --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-focal-image --file taikun-image.qcow2`
{% endhint %}



See [Projects - **Create A New Project**](https://itera.gitbook.io/taikun/user-guide-1/manager/projects/creating-a-new-project) or [Guidelines - **Add Cloud Credentials**](https://itera.gitbook.io/taikun/guidelines/create-credentials).
