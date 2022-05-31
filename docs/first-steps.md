#  **From Login to production Cluster**
>I am new in Taikun and I want to create Kubernetes cluster for my application.    
>This is the way how to.

## **Invitation Mail from Taikun, Reset Password & Login**
[:fontawesome-solid-user:](../user/login) **User**
[:fontawesome-solid-user-tie:](../manager/login/) **Manager**
[:fontawesome-regular-handshake:](../partner/login/) **Partner**


If you are completely new to Taikun, you will receive an invitation to your organization. First you need to reset your password (through *Visit* button in received mail) and then you are redirected right to Taikun login page. By filling *E-mail* and newly created *Password*, you will login to Taikun. First page you see is the Dashboard of your organization.

If [**Keycloak**](https://www.keycloak.org) is set for your organization, you can use it to login.  

<figure markdown>
  ![First Login](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/first-steps/login.gif "First Login")   
  <figcaption>Figure.1: First login</figcaption>
</figure>

If you [**forget your password**](../guidelines/login/#forgotten-password), you can reset it.   

See how to change your password [**here**](../guidelines/change-mail-password/#change-password) and how to change your e-mail [**here**](../guidelines/change-mail-password/#change-e-mail).

## **Add Cloud Credentials**
[:fontawesome-solid-user-tie:](../manager/cloud-credentials/) **Manager**
[:fontawesome-regular-handshake:](../partner/cloud-credentials/) **Partner**

Before you can create your own project, you have to add a cloud. Now you can choose from OpenStack, AWS or Azure.   
You just have to fill in correct credentials from your account and Taikun will connect with them.

### **OpenStack**

Before connecting the openstack cloud, you have to fulfill the [requirements](../guidelines/add-cloud-credentials/#openstack).

<figure markdown>
  ![OpenStack Cloud Credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/add-cc-openstack.gif "OpenStack Cloud Credentials")   
  <figcaption>Figure.2: Openstack cloud credentials</figcaption>
</figure>
   
If you have trouble adding openstack credentials, see [how fill the fields](../guidelines/add-cloud-credentials/#openstack) and [where to find credentials](../guidelines/add-cloud-credentials/#openstack_1).

### **AWS**

<figure markdown>
  ![AWS Cloud Credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/add-cc-aws.gif "AWS Cloud Credentials")
  <figcaption>Figure.3: AWS cloud credentials</figcaption>
</figure>

If you have trouble adding AWS credentials, see [how fill the fields](../guidelines/add-cloud-credentials/#amazon-web-services) and [where to find credentials](../guidelines/add-cloud-credentials/#aws).

### **Azure**

Before connecting the cloud you have to [create application registration](../guidelines/add-cloud-credentials/#azure) through commands.

<figure markdown>
  ![Azure Cloud credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/first-steps/add-cc-azure.gif "Azure Cloud Credentials")
  <figcaption>Figure.4: Azure cloud credentials</figcaption>
</figure>

If you have trouble adding Azure credentials, see [how fill the fields](../guidelines/add-cloud-credentials/#azure) (at the bottom of the page) and [where to find credentials](../guidelines/add-cloud-credentials/where-to-find-credentials/#azure_1).

## **Project Creation**
[:fontawesome-solid-user-tie:](../manager/projects/creating-a-new-project/) **Manager**
[:fontawesome-regular-handshake:](../partner/projects/creating-a-new-project/) **Partner**

After you have successfully added cloud credentials, you can add a project! During project creation, you can choose a lot of features.

<figure markdown>
  ![Add Project](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/first-steps/add-project.gif "Add Project")
  <figcaption>Figure.5: Add project</figcaption>
</figure>

In *Access Profile*, *Alerting Profile* and *Kubernetes Profile* you have by default option *default*. These profiles are created with every new organization. You can also create a new profile and then choose from drop-down selection. If you want to enable backup, you have to add backup credentials first, same with policy profile.  

Some of these features can be added/enabled after project is created: add/detach *alerting* or *policy profile*, enable *monitoring* or *backup*, add *expiration date*.

???+ warning
    **ACCESS PROFILE**
    If you want to use your access profile in a project, you have to create it BEFORE and choose it from drop down selection DURING project creation.   
    After the project is created you cannot add an **ACCESS PROFILE**   

Project can be created only by manager or partner, who then has to assign the project to the user (if they want them to have access to the project).   
More information about project creation for [Manager](../manager/projects/creating-a-new-project/) and [Partner](../manager/projects/creating-a-new-project/).

## **Creating a Cluster**
[:fontawesome-solid-user:](../user/projects/project-details/#add-server) **User**
[:fontawesome-solid-user-tie:](../manager/projects/project-details/#add-server) **Manager**
[:fontawesome-regular-handshake:](../partner/projects/project-details/#add-server) **Partner**

For a functional cluster you need one bastion, at least one kubemaster and at least one kubeworker.

???+ info 
    Recommendation for sizing:
    - *bastion* recommended 2 vCPU + 2GB of RAM
    - *masters*  recommended 4 vCPU + 8GB of RAM

<figure markdown>
  ![Create Cluster](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/first-steps/create-cluster.gif "Create a Cluster")
  <figcaption>Figure.6: Create cluster</figcaption>
</figure>

You can add and delete servers until you are satisfied with the cluster, then you can commit your changes.

You can update some of the features either directly from **Project Details** (depend on role permissions - [User](../user/projects/project-details/), [Manager](../manager/projects/project-details/), [Partner](../partner/projects/project-details/)) like enable backup, enable/disable monitoring, attach/detach alerting profile or under specific tabs like updating *Access Profile*, *Kubernetes Profile*.

Please keep in mind that some changes need *Repair*, which takes some time (e.g. updating *Access Profile*).

See more information about [**cluster creation**](../guidelines/creating-a-cluster/).

## **Kubeconfigs**
[:fontawesome-solid-user:](../user/projects/project-details/#kubeconfigs) **User**
[:fontawesome-solid-user-tie:](../manager/projects/project-details/#kubeconfigs) **Manager**
[:fontawesome-regular-handshake:](../partner/projects/project-details/#kubeconfigs) **Partner**

Add kubeconfig to organize information about clusters, users, namespaces, and authentication mechanisms.

<figure markdown>
  ![Add Kubeconfig](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/first-steps/kubeconfig.gif "Add Kubeconfigs")
  <figcaption>Figure.7: Add kubeconfig</figcaption>
</figure>

More about kubeconfigs for [User](../user/projects/project-details-k8s/#kubeconfigs), [Manager](../manager/projects/project-details-k8s/#kubeconfigs) and [Partner](../partner/projects/project-details-k8s/#kubeconfigs).
