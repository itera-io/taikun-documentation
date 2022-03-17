# **Kubernetes Profiles**

Each Profile is characterized by *ID*, *Name*, *Organization Name*, *CNI* (Container Network Interface), *Octavia*, *Proxy on Bastion*, *Projects* and *Actions*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/kubernetes-profiles/kubernetes-profiles.png "Kubernetes profiles")
  <figcaption>Fig .1: Kubernetes profiles</figcaption>
</figure>

Expand the table to see the last modification (*Last Modified* and *Last Modified By*).

## **Add Kubernetes Profile**

You can create a new profile where you can enable a few features, which you can customize with CNI plugin.

<figure markdown>
  ![Add Kubernetes Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/kubernetes-profiles/add-kubernetes-profile.png "Add Kubernetes Profile")
  <figcaption>Fig .2: Add kubernetes profile</figcaption>
</figure>

*Profile Name* - name for your kubernetes profile (3-30 characters)

**Enable Octavia**

Exposes the Service externally using the load balancers from OpenStack.

**Enable Taikun Load Balancer**

Manage your traffic, only available for OpenStack and Octavia disabled.

**Enable proxy on bastion**

Exposes the Service on each Node's IP at a static port, the NodePort. You'll be able to contact the NodePort Service, from outside the cluster, by requesting <NodeIP\>:<NodePort\>.

**Allow Scheduling on Master**

Schedule Pods on control-plane node to maximize resource usage, but we do not recommend it.


???+ info
     Choose this profile with enabled features during [project creation](../projects/creating-a-new-project).

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Un/Lock the profile to dis-/enable it from drop-down selection when a new project is created, you cannot lock default profile.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete the profile if it is no longer needed. Only profiles with no associated projects can be deleted. You cannot delete default profile.
