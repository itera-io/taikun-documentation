# **Standalone Profiles**

???+ warning
    You **cannot** add a new *VM* without any *standalone profile*, please create a new one first.

See all profiles created for your organization. Each profile is described by its *ID*, *Name*, *Public Key*, *Security Group* (redirects to another page) and to which VM *the profile is associated*.

<figure markdown>
  ![Standalone Profiles](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/standalone-profiles/overview.png "Standalone Profiles")
  <figcaption> Figure.1: Standalone Profiles </figcaption>
</figure>

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Un/lock profile - if you lock your profile, you can't use it for VM, edit or delete it

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/edit.png){: .middle} Update profile - edit *Name*

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete - delete non-used and unlocked profiles


## **Add Standalone Profile**

Create a new profile to access your virtual machine.

<figure markdown>
  ![Add Standalone Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/standalone-profiles/add-profile.png "Add Standalone Profile")
  <figcaption> Figure.2: Add Standalone Profiles </figcaption>
</figure>


*Name* - choose name for your profile

*Public Key* - insert your SSH public key to access the *VM**

*Security Groups* - optional, protocols **ICMP**, **TCP** and **UDP** are supported

???+ warning
    Once the *profile* is created *SSH key* **cannot** be edited.
