# **Project Details-K8s**

By clicking the selected project you are redirected to the **Servers**. Here you can see all servers for the project with their description.

<figure markdown>
  ![Accessing project's details](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/access-project-details.gif "Accessing Project's Details")
  <figcaption>Fig. 1: Accessing project's details</figcaption>
</figure>

## **Project Info**

Under **Servers** title is a brief description of a project - such as *Project Name*, *Project Status*, *Cloud Type*, *Kubernetes Version*, *Access Profile*,  *Cloud Credentials*, *Kubernetes Profile*, *Alerting Profile*, *Access IP Address* (if you use this address 
 to ssh connect, please do not use user ubuntu, it's in use by Taikun for managing the cluster) and _Kubernetes Health_. Some of these include links to e.g. cloud or profiles.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/project-info.png "Project Info")
  <figcaption>Fig. 2: Brief Project Info</figcaption>
</figure>

You can also see here ETC=Estimated Time to Complete. It is approx time (in minutes) until the cluster will be completed.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/etc.png "ETC")
  <figcaption>ETC</figcaption>
</figure>

## **Servers**

Every server is described by *ID*, *Server Name*, *IP Address*, *Flavor*, *CPU/RAM/Disk Size*, *Role*, *Status*, *Kuebernetes Health*, *Creation Time and Actions*. If you expand the table, you can see the last modification made (*Last Modified*, *Last Modified By*).

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/servers.png "Servers for K8s Project")
  <figcaption>Fig. 3: Servers for Project</figcaption>
</figure>

Server status can be:

* Deleting
* Failure
* Pending
* Pending Delete
* Pending Upgrade
* Ready
* Updating
* Upgrading

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show-status.png "Show Status"){: .middle}Show Status - shows current status from the cloud for 3 seconds

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/reboot.png "Reboot"){: .middle} Reboot - choose HARD or SOFT reboot for each server

* HARD - the power to the system is physically turned off and back again causing an initial boot
* SOFT - system restarts without the need to interrupt the power

???+ info
    Hard or soft reboot can be chosen only for Openstack.
    For AWS and Azure there is only simple reboot available.


## **Actions Buttons**

### **Upgrade**

Upgrade your version of Kubespray to the latest one. The button is disabled, if your Kubernetes are up to date. Enabling [auto upgrade](#upgrade) during the project creation, the Upgrade button won't be available.

### **Enable/Disable Backup**

You can *Enable Backup* if you have added the credentials in [**Backup Credentials**](../../backup-credentials) and the project isn't locked. You can do it during the project creation or after the project is created, more info [**here**](../../../guidelines/backup-monitoring-lock-reboot#enable-disable-backup).

After you enable the backup, you get notified through *Notification* and you can check the successful status in Kubernetes. In Projects - Kubernetes - *Deployment* section you should see *velero* installed

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/velero.gif "Velero tool")
  <figcaption>Fig. 4: Velero tool</figcaption>
</figure>

After enabling backup, you should add [**Backup Policies**](#backup-policy).

### **Enable/Disable Monitoring**

Be able to see detailed processes with enabling monitoring. After you enable it, which takes up to 5 minutes, you can preview all tracks with [**Logs**](#logs) button. The tracking starts the moment Logs button is enabled.

You can enable monitoring before project creation or (if you forgot or have changed your mind) whenever your project is created.

Disable function works the same.


### **Commit**

Sends the changes to repository.

Once the cluster is committed you will see [**ETC**](#project-info) in project info.

### **Repair**

When the server's are *Failed* or there is some other problem in the cluster, it can be repaired by changing the status to *Ready*. If all the servers have failed during the first creation, the repair button works as commit and you should use it. If only one server is failed, you should change only the one server's status, because repair will restart the status of all servers.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/repair.gif "Repair")
  <figcaption>Fig. 5: Repair</figcaption>
</figure>

### Attach/Detach Alerting Profile

Attach [**Alerting Profile**](../../alerting-profiles) if you want to receive a notifications about alerts in your project. Detach if notifications are no longer needed.


### **Lock/Unlock**
![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png "lock"){: .middle}**Lock**/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png "unlock"){: .middle}**Unlock**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png "lock"){: .middle} Project is unlocked

Clicking the button you lock a project. You can preview some pages (e.g. *Kube Info*), but you can't make any changes in the project (see [Project Details - **Project info**](#project-info)).

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png "unlock"){: .middle} Project is locked

Clicking the button you unlock a project and enable action buttons.


### **Add Server**

To create a new server click![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/add-server-btn.png "Add server"){: .middle} button and fill all the fields.

You will receive an error message if no flavor has been bound to your project yet. You can also bind the flavor during project creation.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/no-flavor-bound.png "No flavor bound")

Use the link to bind a flavor.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/add-workers.gif "Add servers")
  <figcaption>Fig. 6: Add Server</figcaption>
</figure>

*Server Name* - only alphanumeric characters and dash are allowed, 1-30 characters

???+ warning
    Letters must be lowercase!

*Disk size* - should be at least 30GB

*Role* - you are able to choose from several roles for your servers, which are set according to Kubernetes settings

*Flavor* - choose from the list of offered flavors (e.g. n0.xlarge)

* you can bind the flavors from clouds to the project in [**Flavor Info**](../../flavor-info/)

???+ info
    Recommendation for sizing:

* *bastion* recommended 2 vCPU + 2GB of RAM
* *masters* recommended 4 vCPU + 8GB of RAM

*Number of Servers* - set number for kubeworker or kubemaster, add odd number of masters (min. 3 for a highly available cluster)

???+ warning
The change **MUST** be committed.


*Kubernetes Node Labels* - label nodes where you want to sent or restrict pods; you can add more labels with add label button, for more info see [Kubernetes docs](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)

For more information see [**Creating a Cluster**](../../../guidelines/creating-a-cluster).

**Function buttons**

Between *Project Info* and *Servers* are buttons with specific features or more detailed information.


### **Delete**

Delete the selected server's. You can delete servers to still have a working cluster (1 bastion, 1 master and 1 worker) or delete the whole working cluster.

???+ warning
    The change **DOES NOT** have to be committed.


### **History**

This button will redirect you to Audit Log with pre-filled organization and project, so you can preview the changes made for the chosen project.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/history.gif "History")
  <figcaption>Fig. 7: History</figcaption>
</figure>

### **Kubeconfigs**

Add a new kubernetes configuration for your profile and project.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/add-kubeconfig.png "Add kubeconfig")
  <figcaption>Fig. 8: Add Kube Config</figcaption>
</figure>

*Kubeconfig Name* - choose a name for your kubeconfig

*Kubeconfig Role*

* cluster-admin - perform any action on any resource, ClusterRoleBinding - gives full control over every resource in the cluster and in all namespaces (or in very resource in the role binding's namespace - RoleBinding)
* admin - RoleBinding - allows read/write access to most resources in a namespace, does not allow write access to resource quota or to the namespace itself&#x20;
* edit - allows read/write access to most objects in a namespace, does not allow viewing or modifying roles or role bindings, allows accessing Secrets and running Pods as any ServiceAccount in the namespace
* view - see most objects in a namespace, does not allow viewing roles or role bindings, does not allow viewing Secrets

???+ info
    For more info, see [kubernetes documentation](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#user-facing-roles).

*Application kubeconfig* - choose if kubeconfig can be used by other users (*all* or *managers only*) or *Personal kubeconfig* - kubeconfig can be used only by you

You can see all project's configurations in the table with its *ID*, *Name*, *User Name*, *User Role*, *Project*, *Accessible for all* and *Actions*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/kubeconfig-overview.png "Kube Config")
  <figcaption>Fig. 9: Kubeconfigs</figcaption>
</figure>

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/download.png "download"){: .middle} This .yaml file can be download and use to organize information about clusters, users, namespaces, and authentication mechanisms.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "delete"){: .middle} Delete your kube config if it is no longer needed. You can also delete *user's* or *manager's* kube configs.


### **Kube Info**

If Kubernetes is active, Kube Info button will take you to the Kubernetes configuration. For more see [Projects - **Kubernetes**](../kubernetes).


### **Events**

You are redirected to Events, where you can see all Kubernetes changes made in the project. To preview details for more information to each action use![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MJQrhtis3vRAM281R7J%2F-MNwXBGwTT91-bGRAbAb%2F-MNwbz5QiOnItn3vUmwl%2Fshow.png?alt=media\&token=5311f2d7-e998-4d68-b6dd-019933d28424)button. A green strip indicates a successful action, a brown strip indicates a failed action.​

You can sort Events by:

* *Search* field
* Filling *Start* and *End Date*
* Tick *Only failed* to filter failed actions

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/events.png "Events")
  <figcaption>Fig. 10: Events</figcaption>
</figure>

### **Logs**

Preview Kubernetes cluster logs to Grafana.

Logs button is disabled if [**Monitoring is disabled**](#enabledisable-monitoring). To view logs, you must first *Enable Monitoring*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/logs.png "Logs")
  <figcaption>Fig. 11: Logs</figcaption>
</figure>

Write your query and use *Start date* and *End Date* for sorting. You can also expand every message - red is an *added* action,  without color is other log.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/logs-details.png "Logs details")
  <figcaption>Fig. 12: Logs details</figcaption>
</figure>

### **Alerts**

First thing when you access Alerts are *Firing Alerts*. This section is refreshed every 5 minutes, but you can also use the refresh button to see the most updated data.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/firing-alerts.gif "Firing Alerts")
  <figcaption>Fig. 13: Firing alerts</figcaption>
</figure>

To see all alerts, use upper right *Show All Alerts* button. As seen above, firing alerts are marked with red color.

You can *silence* alert and sort all the alerts by firing, silenced, all or resolved.

Alerts are accessible only if *Monitoring* is enabled and the project is not empty.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/firing-alerts-metrics.gif "Alerts to Metrics")
  <figcaption>Fig. 1: Alerts</figcaption>
</figure>

For each alert you can see details and use a link that will redirected you to [**Metrics**](#metrics) with the query already filled.

The index number at *Alerts* shows the number of firing alerts. ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/alerts-index-number.png){: .middle} When the firing alerts are resolved, the number disappears.

Firing alerts also work from the real-time notifications bell :bell: in header.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/firing-alerts-notification.gif "Alerts notifications"){: .middle}
  <figcaption>Fig. 15: Alerts bell</figcaption>
</figure>

The notification contains a brief message on a specific project and bellow the message is time of the change. After clicking *Show Project*, you can access the project in which the alert is.

As the name suggests: *Mark as Read* and *Dismiss all*.

### **Metrics**

Write a query, search Prometheus Metrics and preview the value needed.

Modify *Step* or *Date*.

Switch between *Console* and *Graph* for better results.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/metrics.gif "Metrics")
  <figcaption>Fig. 16: Metrics</figcaption>
</figure>

### **Backup Policy**

After you [**Enable Backup**](../project-details#enable-disable-backup), you have to create a *Backup Policy*. After clicking the *Backup Policy* button you get redirected to the new page, where you create a new policy with *Add Policy* button.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/backup-policy-restores.png "Add Policy")
  <figcaption>Fig. 17: Add Policy</figcaption>
</figure>

*Name* - choose a name for your backup (3-30 characters)

*Retention period* - how long you want to keep the backup (format e.g. 72h)

*Cron period* - how often you want to do the backup

* predefined - choose from selection from the most common periods
* custom - if you want to specify your own period  (format \* \* \* \* \*)
  *   e.g. every hour - 0 \* \* \* \*; daily - 0 0 \* \* \*, weekly on Sunday - 0 0 \* \* 0

      [crontab guru](https://crontab.guru) with [examples](https://crontab.guru/examples.html)

*Add Include/Exclude Namespace* - specify the special requests that you  want to include or exclude from  the backup, at least one must be filled

???+ info
    The backup is done with a **snapshot method** - backup copy used to create the entire copy of servers every chosen time period.

There are three tabs:

**Schedules**

In *Schedules* you can find overview of your backup policy.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/backup-policy-schedules.png "Schedules")
  <figcaption>Fig. 18: Schedules</figcaption>
</figure>

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show-description.png "show description"){: .middle} *Show description* - see detailed e.g. specification, metadata etc.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "delete"){: .middle} *Delete* - stop the backup by deleting the policy


**Backups**

*Backups* contain backups from schedules.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/backup-policy-backups.png "Backups")
  <figcaption>Fig. 19: Backups</figcaption>
</figure>

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show-description.png "show description"){: .middle} *Show description* - see detailed e.g. specification, metadata etc.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/reset.png "restore backup"){: .middle} *Restore backup* - if anything goes wrong, you can restore the backup, which you will then see in *Restores* tab

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "delete"){: .middle} *Delete* - delete the backup


**Restores**

Overview of restores from *Backups*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/projects/project-details/backup-policy-restores.png "Restores")
  <figcaption>Fig. 20: Restores</figcaption>
</figure>

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show-description.png "show description"){: .middle} *Show description* - see detailed e.g. metadata etc.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "delete"){: .middle} *Delete* - delete the restore

### **Dashboard**

Dashboard is accessible only if cluster is created and [monitoring is enabled](#enabledisable-monitoring).


<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/dashboard.gif "Project Dashboard")
  <figcaption>Fig. 21: Dashboard</figcaption>
</figure>

Here you can see graphs with *Memory* and *CPU* usage for the project. You can also add **Query** you want.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/project-details/dashboard-query.png "Add Query")
  <figcaption>Fig. 22: Add Predefined Query</figcaption>
</figure>

*Name* - choose name for your query (e.g. My Query)

*Expression* - fill in [*Metrics*](#metrics) data (e.g. node\_procs\_running)

*Description* - describe your query (e.g. Node Process Running)

*Category Name* - choose category for your query (e.g. Nodes)
