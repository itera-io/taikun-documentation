---
description: Sign with Your Credential
---

# Add Cloud Credentials

[Manager](https://itera.gitbook.io/taikun/user-guide-1/manager/cloud-credentials)/[Partner](https://itera.gitbook.io/taikun/user-guide-1/partner/cloud-credentials): Use your Credentials to sign to your Cloud in OpenStack, Amazon or Azure.

If you are struggling with adding the clouds, try [Where to find credentials](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials) tab.

Here are examples for each cloud:

## Openstack

### Requirements for Openstack

{% hint style="danger" %}
For Openstack: a taikun image must already exist in the openstack cloud. Requirement is an Ubuntu 20 image and we recommend using a recent kernel, e.g. a base Ubuntu image with hwe kernel here: [https://repo.itera.io/repository/images/taikun-image.qcow2](https://repo.itera.io/repository/images/taikun-image.qcow2)

To use the image in Taikun you have to use the tags "taikun" and "ubuntu{number}”. By default Taikun will take image with the latest {number}.

Command to add an image to openstack:
{% endhint %}

`openstack image create --disk-format qcow2 --container-format bare --public --tag taikun --tag ubuntu20.04 --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-focal-image --file taikun-image.qcow2`

Add new CC:

![Openstack](<../../.gitbook/assets/add openstack.gif>)

_Cloud Name_ - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

_User -_ your user name to OpenStack (e.g. user)

_Password_ - your password to OpenStack (e.g. 123abc)

_URL_ - Endpoint-Identity (e.g. https://cloud.mycloud.com:32132)

_Domain_ - insert domain name (e.g. default)

_Project_ - select Project if there are multiple options (e.g. my-cloud-project)

_Region_ - select Region if there are multiple options (e.g. RegionOne

_Public Network_ - choose network, if available (e.g. public2)

Optional:

_Specify Availability Zone_ - check if you want to specify (e.g. pod04)

_Volume Types_ - check and choose type of volume (e.g. ssd)

_Enable Import Network_ - check if you want to enable

{% hint style="danger" %}
If you choose to import network, DNS in profile created in [_Access Profiles_](https://itera.gitbook.io/taikun/user-guide-1/manager/access-profiles) will be IGNORED.
{% endhint %}

![](<../../.gitbook/assets/enable import network.png>)

{% hint style="warning" %}
If the Credentials are invalid, you are notified and you won't be able to connect the cloud.
{% endhint %}

## Amazon Web Services

![AWS](<../../.gitbook/assets/add awx.gif>)

_Cloud Name_ - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

_Access Key ID_, _Secret Access Key -_ find your credentials in AWS account (under [_My Security Credentials_](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#aws))

_Region_ - choose suitable region

_Availability Zone_ - choose availability for the region

## Azure

Before adding the Azure account, you have to create application registration with commands. ([source](https://github.com/kubernetes-sigs/kubespray/blob/master/docs/azure.md))

{% hint style="info" %}
This process is linux based, there might be some changes for other OS.
{% endhint %}

1\) If you haven't install Azure CLI, you can do it with

```
sudo apt install azure-cli -y
```

2\) Login

```
sudo apt-get install azure-cli
```

You will be redirected to azure web page where you choose your account.

![Web login](<../../.gitbook/assets/azure web.png>)

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

_CLIENT\_SECRET_ - change to your secret (can be deleted later) (e.g. "Ue9)Qj^V\~UYES3(C")

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
    "value": "user_impersonation"
  }
...
}
```

**CLIENT ID** = "appId": "7bxxxxc3-xxxx-4d74-xxxx-8c40xxxb558"

4\) Create service principal for the app

```
az ad sp create --id appId
```

_appId_ is provided from previous command, in this case:

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

_SUBSCRIPTION\_ID_ - subscription id from login command, in this case:

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



Now you have all Azure Ids needed, but you can also find them in [**Azure portal**](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#azure).

Please be careful when inserting the credentials. If you add incorrect credentials, you will not be able to add flavor and then create cluster.



![Azure](<../../.gitbook/assets/add azure.gif>)

_Cloud Name_ - choose name for your Cloud Credentials (3-30 characters, e.g. cloud-test)

_Location_ - choose suitable location

_Availability Zone_ - choose zone for the location
