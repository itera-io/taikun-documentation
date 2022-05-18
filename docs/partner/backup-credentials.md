---
tags:
  - Partner
  - Backup Credentials
hide:
  - tags
---

# **Backup Credentials**

*Select organization* for a better overview of servers for individual projects.

## **Create new credentials**

<figure markdown>
  ![Fig. 1: Add Credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/backup-credentials/add-backup-cred.png "Add Backup Credentials")
  <figcaption>Fig. 1: Add Credentials</figcaption>
</figure>


*Organization* - choose organization from drop-down selection

*S3 Name* - name for backup credentials (3-30 characters)

Fill the remaining S3 data from Amazon and add new backup credentials. See [**endpoints**](https://docs.aws.amazon.com/general/latest/gr/s3.html) from AWS.

**Invalid S3 credentials** error can pop up if you fill in wrong/non-existent credentials.

After you add the credentials, you can backup the project by [**Enable Backup**](../projects/project-details-k8s#enabledisable-backup) and add [**Backup** **Policy**](../projects/project-details-k8s#backup-policy)**.**

## **Backup credentials**

Use the search field for finding the credentials needed.

Every Credential has its:

* ID
* Organization
* S3 Access Key ID
* S3 Endpoint
* S3 Name
* Associated Projects
* Actions

<figure markdown>
  ![Fig. 2: Backup credentials](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/backup-credentials/backup-credentials.png)
  <figcaption>Fig. 2: Backup credentials</figcaption>
</figure>


*ID* and *Organization* are immutable.

*S3 Access Key ID*, *S3 Endpoint* and *S3 Name* are security credentials.

In *Associated Projects* are listed all projects using these backup credentials.

*Created By* informs you who has made the last change.

Look [**here**](../../guidelines/create-credentials/where-to-find-credentials#aws), if you don't know where to find your AWS credentials.

By expanding the table, you can see the last modification made (*Last Modified*, *Last Modified By*).

### **Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/make-default.png){: .middle} Make default - choose credentials which will be then filled during project creation, lighter color indicates selected credentials

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Lock/Unlock Credential - if you lock the Credentials, you disable it for Backup and cannot be deleted. Unlock it to enable it again.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete - you can delete only empty Backup Credentials


For some example see [Guidelines - **Backup**](../../guidelines/backup-monitoring-lock-reboot/#enabledisable-backup).
