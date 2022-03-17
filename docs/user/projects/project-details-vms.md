# **Project Details - VMs**

By clicking *VMs* button in Servers page or VMs *View* in Project page you are redirected to the **VMs Servers**. Here you can see all virtual machines for the project with their description.

<figure markdown>
  ![Accessing Project's details - VMs](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/servers-vms.gif "Accessing Project's Details")
  <figcaption>Fig .1: Accessing project's details</figcaption>
</figure>

## **Project Info**

Under **Servers** title is a brief description of the project - such as *Project Name* (with locked/unlocked image), *Project Status*, *Cloud Type* or *Cloud Credentials*.

<figure markdown>
  ![Project Info](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/project-details-vms.png "Project Info")
  <figcaption>Fig .2: Project info</figcaption>
</figure>

When there is some operation going on, you can also see here ETC=Estimated Time to Complete. It is approx time (in minutes) until the cluster will be completed.

<figure markdown>
  ![ETC](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/etc.png "ETC")
  <figcaption>Fig .3: ETC</figcaption>
</figure>

## **Servers**

Every Server is described by *ID*, *Name*, *Flavor*, *IP Address*, *Public IP Address*, *Status*, *Profile*, *Image* and *Created*. If you expand the table, you can see the last modification made (*Created By*, *Last Modified*, *Last Modified By*).

<figure markdown>
  ![Servers for Project](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/servers-vms.png "Servers for Project")
  <figcaption>Fig .4: Servers for project</figcaption>
</figure>

Server status can be:

* Deleting
* Failure
* Pending
* Pending Delete
* Pending Upgrade
* Ready
* Updating
* Upgrading

## **Actions**

### **Commit**

Sends the changes to the repository.

Once the cluster is committed you will see ETC in project info.

### **Repair**

When the server's are *Failed*, use repair button.

<figure markdown>
  ![Repair](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/repair.gif "Repair")
  <figcaption>Fig .5: Repair</figcaption>
</figure>

### **Add VM**

To create a new server click![Add VM](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/add-vm-btn.png){: .middle} button and fill all the fields. You, as user, can't delete servers - think twice which and how many servers you want to create.

???+ warning
	For creating the VM: ***Image*** has to be bound and ***Stanalone Profile*** has to be created. Please contact your manager if these fields are empty.

<figure markdown>
  ![Add VM](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details-vms/add-vm.gif "Add VM")
  <figcaption>Fig .6: Add VM</figcaption>
</figure>

*Server Name* - only alphanumeric characters and dash are allowed, 1-30 characters

???+ warning
	Letters must be lowercase!

*Flavor* - choose from the list of offered flavors (e.g. n0.large)

*Image* - choose from the list of offered images (e.g. ubuntu-20.04)

*Volume Size* - minimal size is automatically filled in when you select image, you can only increase the volume size number

*Volume Type* - optional, choose from drop down selection

*Profile* - choose *Standalone profile*

*Count* - how many VMs you want to create

*Public IP* - check if you want to enable public IP

*Cloud-init* - optional, if set it will override the ssh key from standalone profile

*Tags* - enter *Key* and *Value*

*Disk* - enter *Name*, choose *Size* and select *Volume Type*

???+ info
	If the project is locked:lock: which you can see under [**Project Info**](../project-details-k8s/#project-info), you **can't** use *Commit*, *Repair* or *Add VM*.
