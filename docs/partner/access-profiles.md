---
tags:
  - Partner
  - Access Profiles
hide:
  - tags
---

# **Access Profiles**

*Select organization* for a better overview of Access Profiles.

???+ info
    When using ssh to connect to the servers, please **DO NOT** use user **ubuntu**. It is already in use by Taikun for the management of the cluster.

Without internet access and to keep your security, you can download the packages, docker images, etc. using a proxy server.

<figure markdown>
  ![Fig. 1: Access Profiles](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/access-profiles/access-profiles.png "Access Profiles")
  <figcaption>Fig. 1: Access Profiles</figcaption>
</figure>

You can extend the table to see the last modification (*Last Modified* and *Last Modified By*).

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/edit.png){: .middle} Edit Http Proxy - update address

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete access profile, you cannot delete default profile

## **Add Access Profile**

Create a new profile to access a specific project.

<figure markdown>
  ![Fig.2: Add Access Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/access-profiles/add-access-profile.png "Add Access Profile")
  <figcaption>Fig.2: Add Access Profile</figcaption>
</figure>

*Organization* - choose organization form drop down section

*Name* - choose name for a new profile

*Http Proxy* - enter http proxy

*SSH Users* - fill user (3-30 characters) and it's public SSH key

* type of key must be RSA, ECDSA or Ed25519

*DNS* - for access you can also use DNS

???+ danger
    DNS will be ignored, if you choose import network in new [*Cloud Credentials*](../guidelines/add-cloud-credentials).

*NTP* - or use NTP for accessing

If you want to change any of these parameters, you can do it with *Show* button and update the fields.
