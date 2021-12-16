---
description: Create Credentials to Enable Backup
---

# Backup Credentials

_Select organization_ for a better overview of servers for individual projects_._

### Create new credentials

![Fig. 1: Add Credentials](<../.gitbook/assets/add-backup-cred (1).png>)

_Organization_ - choose organization from drop-down selection

_S3 Name_ - name for backup credentials (3-30 characters)

Fill the remaining S3 data from Amazon and add new backup credentials. See [**endpoints**](https://docs.aws.amazon.com/general/latest/gr/s3.html) from AWS.

**Invalid S3 credentials** error can pop up if you fill in wrong/non-existent credentials.&#x20;

After you add the credentials, you can backup the project by [**Enable Backup**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#enable-disable-backup) and add [**Backup** **Policy**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#backup-policy)**.**



### Backup credentials

Use the search field for finding the credentials needed.

Every Credential has its:

* ID
* Organization
* S3 Access Key ID
* S3 Endpoint
* S3 Name
* Associated Projects
* Actions

![Fig. 2: Backup credentials](<../.gitbook/assets/backup (3).png>)

_ID_ and _Organization_ are immutable.

_S3 Access Key ID_, _S3 Endpoint_ and _S3 Name_ are security credentials.

In _Associated Projects_ are listed all projects using these backup credentials.

_Created By_ informs you who has made the last change.

Look [**here**](https://itera.gitbook.io/taikun/guidelines/create-credentials/where-to-find-credentials#aws), if you don't know where to find your AWS credentials.



By expanding the table, you can see the last modification made (_Last Modified_, _Last Modified By_).



### Actions

![](<../.gitbook/assets/make default.png>)Make default - choose credentials which will be then filled during project creation, lighter color indicates selected credentials

![](<../.gitbook/assets/lock (3).png>)/![](../.gitbook/assets/unlock.png)Lock/Unlock Credential - if you lock the Credentials, you disable it for Backup and cannot be deleted. Unlock it to enable it again.

![](<../.gitbook/assets/delete (2).png>)Delete - you can delete only empty Backup Credentials



For some example see [Guidelines - **Backup**](https://itera.gitbook.io/taikun/guidelines/backup-monitoring-lock-reboot#enable-disable-backup).
