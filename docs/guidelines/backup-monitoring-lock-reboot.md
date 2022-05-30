# **Kubeconfigs, Backup, Monitoring, Lock, Reboot**

[:fontawesome-solid-user:](../../user/projects/project-details-k8s/) **User**
[:fontawesome-solid-user-tie:](../../manager/projects/project-details-k8s/) **Manager**
[:fontawesome-regular-handshake:](../../partner/projects/project-details-k8s/) **Partner**

## **Kubeconfigs**

Create and download kuberenetes configuration to organize information about clusters, users, namespaces, and authentication mechanisms.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/kubeconfig.gif)
  <figcaption>Figure.1: Kubeconfig</figcaption>
</figure>

???+ info
    Manager/Partner: You can see and delete other user's kube configs, but you cannot use them for connecting, if the kubeconfig is not for everyone.
    User: You can use and delete only your kube config.

See info for [User](../../user/projects/project-details-k8s/#kubeconfigs), [Manager](../../manager/projects/project-details-k8s/#kubeconfigs) and [Partner](../../partner/projects/project-details-k8s/#kubeconfigs).

???+ warning
    The following features are only for **Manager** and **Partner**.

## **Enable/Disable Backup**

1\) If you want to have a backup, first you must add Backup credentials:

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/backup-credentials/add-backup-credentials.png)
  <figcaption>Figure.2: Add backup credentials</figcaption>
</figure>

Fill all fields for S3 credentials and add connect them with add button.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/backup-credentials/backup-credentials.png)
  <figcaption>Figure.3: Backup credentials overview</figcaption>
</figure>

2\) Enable backup.

a) You can enable backup during creation.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/enable-backup-project-creation.gif)
  <figcaption>Figure.4: Enable backup</figcaption>
</figure>

b) Backup can be enabled also after the project is created.

First you have to enable back and then choose credentials.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/enable-backup-after-project-creation.gif)
  <figcaption>Figure.5: Backup after project creation</figcaption>
</figure>

4\) After you enabled backup, you must set up backup policy

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/add-backup-policy.gif)
  <figcaption>Figure.6: Backup policy</figcaption>
</figure>

???+ warning
    Once the policy is add, the cronjob starts.

More info for [Manager](../../manager/projects/project-details-k8s/#backup-policy) and [Partner](../../partner/projects/project-details-k8s/#backup-policy).

5\) To terminate the backup, delete the policy.

6\) If you no longer want to use back, disable it

## **Enable/Disable Monitoring**

1\) Enable monitoring during creation of the project.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/enable-monitoring-project-creation.gif)
  <figcaption>Figure.7: Enable monitoring during project creation</figcaption>
</figure>

2\) Or you can enable monitoring after you create the project.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/enable-monitoring-after-project-creation.gif)
  <figcaption>Figure.8: Enable monitoring after project creation</figcaption>
</figure>

The process takes up to 2 minutes and if successful, *Logs, Alerts* and *Metrics* are enabled.

3\) Disable Monitoring the same way.

## **Lock/Unlock**

If Manager/Partner lock the project, you can only preview some pages but you can't make any changes (actions).

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/lock-project.gif)
  <figcaption>Figure.9: Locked project</figcaption>
</figure>

You can see if the project is![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle} unlock or![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} locked in project info:

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/lock-project-info.png)
  <figcaption>Figure.10: Lock - project info</figcaption>
</figure>

or in Project overview - *Actions* section:

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/lock-actions.png)
  <figcaption>Figure.11: Lock - project overview</figcaption>
</figure>

## **Reboot**

You can reboot servers directly from Taikun.

For Openstack you can choose HARD or SOFT reboot for each server.

For AWS and Azure there is only simple reboot available.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/guidelines/kubeconfigs-backup-monitoring-lock-reboot/reboot.gif)
  <figcaption>Figure.12: Reboot</figcaption>
</figure>

For more info see:

* User - [Project Details](../../user/projects/project-details-k8s/)
* Manager - [Project Details](../../manager/projects/project-details-k8s/)
* Partner - [Project Details](../../partner/projects/project-details-k8s/)
