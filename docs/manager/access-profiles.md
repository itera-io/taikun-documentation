---
description: Create a Profile for an Offline Connection
---

# Access Profiles

{% hint style="info" %}
When using ssh to connect to the servers, please **DO NOT** use user **ubuntu**. It is already in use by Taikun for the management of the cluster.
{% endhint %}

Without internet access and to keep your security, you can download the packages, docker images, etc. using a proxy server.

![Fig. 1: Access Profiles](<../.gitbook/assets/access profile (2).png>)

You can extend the table to see the last modification (_Last Modified_ and _Last Modified By_).

#### Actions

![](../.gitbook/assets/edit.png)Edit Http Proxy - update access profile

![](<../.gitbook/assets/delete (2).png>)Delete access profile, you cannot delete default profile



### Add Access Profile

Create a new profile to access a specific project.

![Fig.2: Add Access Profile](<../.gitbook/assets/add access profile (4).png>)

_Name_ - choose name for a new profile, 3-30 characters

_Http Proxy_ - enter http proxy

_SSH Users_ - fill user (3-30 characters) and it's public SSH key

* type of key must be RSA, ECDSA or Ed25519

_DNS_ - for access you can also use DNS

{% hint style="danger" %}
DNS will be ignored, if you choose import network in new [_Cloud Credentials_](https://itera.gitbook.io/taikun/guidelines/create-credentials).
{% endhint %}

If you want to change any of these parameters, you can do it with _Show_ button and update the fields.
