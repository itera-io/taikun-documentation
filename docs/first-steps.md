---
description: >-
  I am new in Taikun and I want to create Kubernetes cluster for my application.
  This is the way how to
---

# From Login to production Cluster

## Invitation Mail from Taikun, Reset Password & Login

If you are completely new to Taikun, you will receive an invitation to your organization. First you need to reset your password (through _Visit_ button in received mail) and then you are redirected right to Taikun login page. By filling _E-mail_ and newly created _Password_, you will login to Taikun. First page you see is Dashboard of your organization.

If [**Keycloak**](https://www.keycloak.org) is set for your organization, you can use it to login.

![First Login](<.gitbook/assets/visit, reset password, login (1).gif>)

If you [**forget your password**](https://itera.gitbook.io/taikun/guidelines/login#forgotten-password), you can reset it.

See how to change your password **** [**here**](https://itera.gitbook.io/taikun/guidelines/verify-the-e-mail-address-and-change-the-password#change-password) and how to change your e-mail **** [**here**](https://itera.gitbook.io/taikun/guidelines/verify-the-e-mail-address-and-change-the-password#change-e-mail).



## Add Cloud Credentials

Before you can create your own project, you have to add a cloud. Now you can choose from OpenStack, AWS or Azure.

You just have to fill in correct credentials from your account and Taikun will connect with them.



### OpenStack

Before connecting the openstack cloud, you have to fulfill the [requirements](https://itera.gitbook.io/taikun/guidelines/create-credentials#openstack).

![OpenStack Cloud Credentials](<.gitbook/assets/add openstack.gif>)

If you have trouble adding openstack credentials, see [how fill the fields](https://itera.gitbook.io/taikun/guidelines/create-credentials#openstack) and [where to find credentials](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#openstack).



### AWS

![AWS Cloud Credentials](<.gitbook/assets/add awx.gif>)

If you have trouble adding AWS credentials, see [how fill the fields](https://itera.gitbook.io/taikun/guidelines/create-credentials#amazon-web-services) and [where to find credentials](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#aws).



### Azure

Before connecting the cloud you have to [create application registration](https://itera.gitbook.io/taikun/guidelines/create-credentials#azure) with commands.

![Azure Cloud credentials](<.gitbook/assets/add azure.gif>)

If you have trouble adding AWS credentials, see [how fill the fields](https://itera.gitbook.io/taikun/guidelines/create-credentials#amazon-web-services) (at the bottom of the page) and [where to find credentials](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#azure).



## Project Creation

After you have successfully added cloud credentials, you can add a project! During project creation, you can choose a lot of features.

![Add Project](<.gitbook/assets/add project (10).gif>)

In _Access Profile_, _Alerting Profile_ and _Kubernetes Profile_ you have by default option _default_. These profiles are created with new organization creation. You can also create a new profile and then choose from drop-down selection. If you want to enable backup, you have to add backup credentials first.

{% hint style="danger" %}
**ACCESS PROFILE**

**If you want to use your access profile in a project, you have to create it BEFORE and choose it from drop down selection DURING project creation.**

**After the project is CREATED you CANNOT ADD ACCESS PROFILE.**
{% endhint %}

Project can be created only by manager or partner, who then has to assign the project to the user (if they want them to have access to the project).

More information about project creation for [**Manager**](https://itera.gitbook.io/taikun/user-guide-1/manager/projects/creating-a-new-project) and [**Partner**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/creating-a-new-project).



## Creating a Cluster

For a functional cluster you need one bastion, at least one kubemaster and at least one kubeworker.

{% hint style="info" %}
Recommendation for sizing:

* _bastion_ recommended 2 vCPU + 2GB of RAM
* _masters_ recommended 4 vCPU + 8GB of RAM
{% endhint %}

![](<.gitbook/assets/create cluster.gif>)

You can add and delete servers until you are satisfied with the cluster, then you can commit (under Actions drop-down).

You can updated almost all the features either directly from **Project Details** ([User](https://itera.gitbook.io/taikun/user-guide-1/user/projects/project-details), [Manager](https://itera.gitbook.io/taikun/user-guide-1/manager/projects/project-details), [Partner](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details)) like enable backup, enable/disable monitoring, attach/detach alerting profile or under specific tabs like updating _Access Profile_, _Kubernetes Profile_.

Please keep in mind that some changes need Repair, which takes some time (e.g. updating _Access Profile_).

See more information about [**cluster creation**](https://itera.gitbook.io/taikun/guidelines/creating-a-cluster).



## Kubeconfigs

Add kubeconfig to organize information about clusters, users, namespaces, and authentication mechanisms.

![Add Kubeconfig](.gitbook/assets/kubeconfig.gif)

More about kubeconfigs for [User](https://itera.gitbook.io/taikun/user-guide-1/user/projects/project-details#kubeconfigs), [Manager](https://itera.gitbook.io/taikun/user-guide-1/manager/projects/project-details#kubeconfigs) and [Partner](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#kubeconfigs).



