---
description: Add New Profile with various features
---

# Kubernetes Profiles

_Select organization_ for a better overview of Kubernetes Profiles.

Each Profile is characterized by _ID_, _Name_, _Organization_ _Name_, _CNI (Container Network Interface)_, _Octavia_, _Proxy on Bastion_, _Projects_ and _Actions_.

![Fig. 1: Kubernetes profiles](<../.gitbook/assets/kubernetes profile (5).png>)

Expand the table to see the last modification (_Last Modified_ and _Last Modified By_).



### Add Kubernetes Profile

You can create a new profile where you can enable a few features, which you can customize with CNI plugin.

![Fig. 2: Add Kubernetes Profile](<../.gitbook/assets/add kubernetes profiel (1).png>)

_Organization_ - choose organization for your profile

_Profile Name_ - name for your kubernetes profile (3-30 characters)

#### Octavia

Exposes the Service externally using the load balancers from OpenStack.

**Enable Taikun Load Balancer**

Manage your traffic, only available for OpenStack and Octavia disabled.

#### Proxy on bastion

Exposes the Service on each Node's IP at a static port, the NodePort. You'll be able to contact the NodePort Service, from outside the cluster, by requesting \<NodeIP>:\<NodePort>.



{% hint style="info" %}
Choose this profile with enabled features during [project creation](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/creating-a-new-project).
{% endhint %}



### Actions

![](<../.gitbook/assets/lock (3).png>)/ ![](../.gitbook/assets/unlock.png)Un/Lock the profile to dis-/enable it from drop-down selection when a new project is created, you cannot lock default profile.

![](<../.gitbook/assets/delete (2).png>) Delete the profile if it is no longer needed. Only profiles with no associated projects can be deleted. You cannot delete default profile.
