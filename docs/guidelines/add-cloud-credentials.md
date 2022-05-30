# **Add Cloud Credentials**

[:fontawesome-solid-user-tie:](../../manager/cloud-credentials) **Manager**
[:fontawesome-regular-handshake:](../../partner/cloud-credentials) **Partner**

If you are struggling with adding the clouds, try [Where to find credentials](#where-to-find-credentials).

Here are examples for each cloud:

## **Openstack**

### **Requirements for Openstack**

???+ warning
    For Openstack: a taikun image must already exist in the openstack cloud. Requirement is an Ubuntu 20 image and we recommend using a recent kernel, e.g. a base Ubuntu image with hwe kernel here: [https://repo.itera.io/repository/images/taikun-image.qcow2](https://repo.itera.io/repository/images/taikun-image.qcow2)

    To use the image in Taikun you have to use the tags "taikun" and "ubuntu{number}”. By default Taikun will take image with the latest {number}.

    Command to add an image to openstack:

    `openstack image create --disk-format qcow2 --container-format bare --public --tag taikun --tag ubuntu20.04 --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-focal-image --file taikun-image.qcow2`

**Add new CC**:

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/add-cc-openstack.gif "Add Openstack Credentials")
  <figcaption>Figure.1: Openstack</figcaption>
</figure>

*Cloud Name* - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

*User -* your user name to OpenStack (e.g. user)

*Password* - your password to OpenStack (e.g. 123abc)

*URL* - Endpoint-Identity (e.g. https://cloud.mycloud.com:32132)

*Domain* - insert domain name (e.g. default)

*Project* - select Project if there are multiple options (e.g. my-cloud-project)

*Region* - select Region if there are multiple options (e.g. RegionOne

*Public Network* - choose network, if available (e.g. public2)

Optional:

*Specify Availability Zone* - check if you want to specify (e.g. pod04)

*Volume Types* - check and choose type of volume (e.g. ssd)

*Enable Import Network* - check if you want to enable

???+ warning
    If you choose to import network, DNS in profile created in [**Access Profiles**](../../manager/access-profiles) will be IGNORED.

![Enable Import Network](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/enable-import-network.png "Enable Import Network")

???+ warning
    If the Credentials are invalid, you are notified and you won't be able to connect the cloud.

## **Amazon Web Services**

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/add-cc-aws.gif "Add AWS")
  <figcaption>Figure.2: AWS - Amazon web service</figcaption>
</figure>

*Cloud Name* - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

*Access Key ID*, *Secret Access Key* - find your credentials in AWS account (under [**My Security Credentials**](#aws))

*Region* - choose suitable region

*Availability Zone* - choose availability for the region


## **Azure**

Before adding the Azure account, you have to create application registration with commands. ([source](https://github.com/kubernetes-sigs/kubespray/blob/master/docs/azure.md))

???+ info
    This process is linux based, there might be some changes for other OS.

1\) If you haven't install Azure CLI, you can do it with

```
sudo apt install azure-cli -y
```

2\) Login

```
sudo apt-get install azure-cli
```

You will be redirected to azure web page where you choose your account.

![Web login](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/azure-web.png "Azure Web Login")

CLI output:

```
[
  {
    "cloudName": "AzureCloud",
    "id": "c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6",
    "isDefault": true,
    "name": "Bezplatná zkušební verze",
    "state": "Enabled",
    "tenantId": "32xxxxb3-xxx-46b3-xxxx-0exxxxc46d1",
    "user": {
      "name": "usermail@gmail.com",
      "type": "user"
    }
  }
]
```

**AZURE SUBSCRIPTION ID** = "id": "c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6"

**AZURE TENANT ID** = "tenantId": "32xxxxb3-xxx-46b3-xxxx-0exxxxc46d1"

3\) Create Azure App

```
az ad app create --display-name kubernetes --identifier-uris http://kubernetes --homepage http://example.com --password CLIENT_SECRET
```

*CLIENT\_SECRET* - change to your secret (can be deleted later) (e.g. "Ue9)Qj^V\~UYES3(C")

**AZURE CLIENT SECRET** = CLIENT\_SECRET

CLI output

```
{
  "acceptMappedClaims": null,
  "addIns": [],
  "allowGuestsSignIn": null,
  "allowPassthroughUsers": null,
! "appId": "7bxxxxc3-xxxx-4d74-xxxx-8c40xxxb558", !
  "appLogoUrl": null,
  "appPermissions": null,
  "appRoles": [],
  "applicationTemplateId": null,
  "availableToOtherTenants": false,
  "deletionTimestamp": null,
  "displayName": "kubernetes",
  "errorUrl": null,
  "groupMembershipClaims": null,
  "homepage": "http://example.com",
  "identifierUris": [
    "http://kubernetes"
  ],
  }
  ...
  {
    "adminConsentDescription": "Allow the application to access kubernetes on behalf of the signed-in user.",
    "adminConsentDisplayName": "Access kubernetes",
    "id": "59xxx87-xxxx-47b8-xxxx-1708xxxxefcd",
    "isEnabled": true,
    "type": "User",
    "userConsentDescription": "Allow the application to access kubernetes on your behalf.",
    "userConsentDisplayName": "Access kubernetes",
    "value": "user*impersonation"
  }
...
}
```

**CLIENT ID** = "appId": "7bxxxxc3-xxxx-4d74-xxxx-8c40xxxb558"

4\) Create service principal for the app

```
az ad sp create --id appId
```

*appId* is provided from previous command, in this case:

az ad sp create -id 7bxxxxc3-xxxx-4d74-xxxx-8c40xxxb558

CLI output:

```
{
  "accountEnabled": true,
  ...
}
...
"objectId": "85xxxxcb-xxxx-4761-xxxx-63fxxxx515e",
  "objectType": "ServicePrincipal",
  "odata.metadata": "https://graph.windows.net/32xxxxb3-xxxx-46b3-xxxx-0e33xxxx46d1/$metadata#directoryObjects/@Element",
  "odata.type": "Microsoft.DirectoryServices.ServicePrincipal",
}
...
```

5\) Create the role assignment

```
az role assignment create --role "Owner" --assignee http://kubernetes --subscription SUBSCRIPTION_ID
```

*SUBSCRIPTION\_ID* - subscription id from login command, in this case:

az role assignment create --role "Owner" --assignee http://kubernetes --subscription c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6

CLI output:

```
{
  "canDelegate": null,
  "id": "/subscriptions/c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6/providers/Microsoft.Authorization/roleAssignments/4fxxxx7f-xxxx-4ccf-xxxx-7287xxxxfa14",
  "name": "4fxxxx7f-xxxx-4ccf-xxxx-7287xxxxfa14",
  "principalId": "85xxxxcb-xxxx-4761-xxxx-63ffxxxx515e",
  "principalType": "ServicePrincipal",
  "roleDefinitionId": "/subscriptions/c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6/providers/Microsoft.Authorization/roleDefinitions/8exxxx57-xxxx-443c-xxxx-2fe8xxxxb635",
  "scope": "/subscriptions/c0xxxxa5-xxx-4ecb-xxxx-f37bxxxx28d6",
  "type": "Microsoft.Authorization/roleAssignments"
}
```

Now you have all Azure Ids needed, but you can also find them in [**Azure portal**](#azure_1).

Please be careful when inserting the credentials. If you add incorrect credentials, you will not be able to add flavor and then create cluster.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/add-cc-azure.gif "Add Azure Credentials")
  <figcaption>Figure.3: Azure</figcaption>
</figure>

*Cloud Name* - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

*Location* - choose suitable location

*Availability Zone* - choose zone for the location

----

## **Where to find credentials**

### **Openstack**

As you should know your *user name* and *password*, after filling the *url*, the other data from Openstack will be seen right in Taikun.

Url

* Api Access - Identity (=Url)

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/openstack-url.png "Openstac-Url")
  <figcaption>Figure.4: Openstack-URL</figcaption>
</figure>

### **AWS**

In AWS console, click *My Security Credentials* under your user. Here you can create a new access key with secret key or you can use your previous one, if you remember the secret key. See docs below.

Access Key Id, Secret Access Key

* User - My Security Credentials - Access keys for CLI, SDK, & API access

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/aws-1.png "AWS 1: User-My Security Credentials")
  <figcaption>Figure.5: AWS 1: User-My Security Credentials</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/aws-2.png "AWS 2: Access keys for CLI, SDK, & API access")
  <figcaption>Figure.6: AWS 2: Access keys for CLI, SDK & API</figcaption>
</figure>

[AWS documentation](https://aws.amazon.com/blogs/security/wheres-my-secret-access-key/)


### **Azure**

If you haven't create you application via CLI, find the right guideline [here](#azure).

Credentials for Azure are in different tabs. Find below where to find them. If you haven't paid your subscription or created secret, find the docs at the end.

Please be careful when inserting the credentials. If you add incorrect credentials, you will not be able to add flavor and then create cluster.

#### **Azure Client and Tenant Id**

* Azure Active Directory - App registrations - All Applications - *application* -> Application (client) ID (=Azure Client Id) and Directory (tenant) ID (Azure Tenant Id)

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-tenant-id-1.png "Azure 1: Azure Active Directory")
  <figcaption>Figure.7: Azure 1: Azure Active Directory</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-tenant-id-2.png "Azure 2: App registration")
  <figcaption>Figure.8: Azure 2: App registration</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/aws-2.png "AWS 2: Access keys for CLI, SDK, & API access")
  <figcaption>Figure.9: Azure 3: All registration: application name</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/aws-2.png "AWS 2: Access keys for CLI, SDK, & API access")
  <figcaption>Figure.10: Azure 4: Client and Tenant ID</figcaption>
</figure>


#### **Azure Secret Id**

* Azure Active Directory - App registrations - All Applications - *application* - Certificates & secrets - Client secrets -> Value (=Azure Secret Id)

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-secret-1.png "Azure 1: Azure Active Directory")
    <figcaption>Figure.11: Azure 1: Azure Active Directory</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-secret-2.png "Azure 2: App registration")
      <figcaption>Figure.12: Azure 2: App registration</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-secret-3.png "Azure 3: Certificates & secrets")
      <figcaption>Figure.13: Azure 3: Certificates & secrets</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-client-secret-4.png "Azure 4: Client secrets Value")
      <figcaption>Figure.14: Azure 4: Client secrets Value</figcaption>
</figure>

???+ warning
    Client Secret is shown only for the first time, we recommend to save it somewhere else.

#### **Azure Subscription Id**

???+ info
    **Subscription is chosen from drop-down selection, but you can find below where to find your Subscription ID.**

* Subscriptions -> Subscription ID (=Azure Subscription Id)

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-subscription-1.png "Azure 1: Subscription")
      <figcaption>Figure.15: Azure 1: Subscriptions</figcaption>
</figure>

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/add-cc/where-to-find-cc/azure-subscription-2.png "Azure 2: Subscription ID")
      <figcaption>Figure.16: Azure 2: Subscription ID</figcaption>
</figure>

[Azure guideline](https://www.inkoop.io/blog/how-to-get-azure-api-credentials/)
