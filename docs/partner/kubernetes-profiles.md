---
tags:
  - Partner
  - Kubernetes Profiles
hide:
  - tags
---

# **Kubernetes Profiles**

*Select organization* for a better overview of Kubernetes Profiles.

Each Profile is characterized by *ID*, *Name*, *Organization Name*, *CNI (Container Network Interface)*, *Octavia*, *Proxy on Bastion*, *Projects and Actions*.

<figure markdown>
  ![Fig. 1: Kubernetes profiles](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/kubernetes-profiles/kubernetes-profiles.png "Kubennetes profiles")
  <figcaption>Fig. 1: Kubernetes profiles</figcaption>
</figure>

Expand the table to see the last modification (*Last Modified* and *Last Modified By*).


## **Add Kubernetes Profile**

You can create a new profile where you can enable a few features, which you can customize with CNI plugin.

<figure markdown>
  ![Fig. 2: Add Kubernetes Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/kubernetes-profiles/add-kubernetes-profile.png)
  <figcaption>Fig. 2: Add Kubernetes Profile</figcaption>
</figure>

*Organization* - choose organization for your profile

*Profile Name* - name for your kubernetes profile (3-30 characters)

#### Octavia

Exposes the Service externally using the load balancers from OpenStack.

**Enable Taikun Load Balancer**

Manage your traffic, only available for OpenStack and Octavia disabled.

#### Proxy on bastion

Exposes the Service on each Node's IP at a static port, the NodePort. You'll be able to contact the NodePort Service, from outside the cluster, by requesting NodeIP:NodePort.

???+ info
    Choose this profile with enabled features during [project creation](../projects/creating-a-new-project).

**Enable Unique Cluster Name**

If not enabled, the cluster name will be cluster.local

### Actions

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Un/Lock the profile to dis-/enable it from drop-down selection when a new project is created, you cannot lock default profile.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete the profile if it is no longer needed. Only profiles with no associated projects can be deleted. You cannot delete default profile.
