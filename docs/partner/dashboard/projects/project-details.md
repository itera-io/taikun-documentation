# Project Details

By clicking the selected project you are redirected to the **Servers**. Here you can see all servers for the project with their description.

![Fig. 1: Accessing project's details](<../../../.gitbook/assets/access servers (3).gif>)



### Project Info

Under **Servers** title is a brief description of a project - such as _Project Name_, _Project_ _Status_, _Cloud_ _Type_, _Kubernetes_ _Version_, _Access Profile_,  _Cloud_ _Credentials_, _Kubernetes_ _Profile_, _Alerting Profile_, _Access IP Address_ (if you use this address to ssh connect, please do not use user ubuntu, it's in use by Taikun for managing the cluster) and _Kubernetes Health_. Some of these include links to e.g. cloud or profiles.

![Fig. 2: Brief Project Info](<../../../.gitbook/assets/label (1).png>)

You can also see here ETC=Estimated Time to Complete. It is approx time (in minutes) until the cluster will be completed.

![ETC](../../../.gitbook/assets/etc.png)



### Servers

Every server is described by _ID_, _Server Name_, _IP Address_, _Flavor_, _CPU/RAM/Disk Size_, _Role_, _Status,_ _Kuebernetes Health_, _Creation Time_ and _Actions_. If you expand the table, you can see the last modification made (_Last Modified_, _Last Modified By_).

![Fig. 3: Servers for Project](<../../../.gitbook/assets/servers (9).png>)

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

![](<../../../.gitbook/assets/show status.png>)Show Status - shows current status from the cloud for 3 seconds

![](<../../../.gitbook/assets/reboot (1).png>) Reboot - choose HARD or SOFT reboot for each server

* HARD - the power to the system is physically turned off and back again causing an initial boot
* SOFT - system restarts without the need to interrupt the power

{% hint style="info" %}
Hard or soft reboot can be chosen only for Openstack.

For AWS and Azure there is only simple reboot available.
{% endhint %}



****

#### **Actions** ![](../../../.gitbook/assets/actions.png)&#x20;

### **Upgrade**

Upgrade your version of Kubespray to the latest one. The button is disabled, if your Kubernetes are up to date. Enabling [auto upgrade](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/creating-a-new-project) during the project creation, the Upgrade button won't be available.

****

### **Enable/Disable Backup**

You can **** _Enable Backup_ **** if you have added the credentials in [**Backup Credentials**](https://itera.gitbook.io/taikun/user-guide-1/partner/backup-credentials) and the project isn't locked. You can do it during the project creation or after the project is created, more info [**here**](https://itera.gitbook.io/taikun/guidelines/backup-monitoring-lock-reboot#enable-disable-backup)**.**

After you enable the backup, you get notified through _Notification_ and you can check the successful status in Kubernetes. In Projects - Kubernetes - _Deployment_ section you should see _velero_ installed

![Fig. 4: Velero tool](<../../../.gitbook/assets/velero (1).gif>)

After enabling backup, you should add [**Backup Policies**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#backup-policy).

****

### **Enable/Disable Monitoring**

Be able to see detailed processes with enabling monitoring. After you enable it, which takes up to 5 minutes, you can preview all tracks with [**Logs**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#logs) button. The tracking starts the moment Logs button is enabled.

You can enable monitoring before project creation or (if you forgot or have changed your mind) whenever your project is created.

Disable function works the same.

****

### **Commit**

Sends the changes to repository.

Once the cluster is committed you will see [**ETC**](https://itera.gitbook.io/taikun/partner/projects/project-details#project-info) in project info.

### **Repair**

When the server/s are _Failed_ or there is some other problem in the cluster, it can be repaired by changing the status to _Ready_. If all the servers have failed during the first creation, the repair button works as commit and you should use it. If only one server is failed, you should change only the one server's status, because repair will restart the status of all servers.

![Fig. 5: Repair](<../../../.gitbook/assets/repair (7).gif>)

###

### Attach/Detach Alerting Profile

Attach **** [**Alerting Profile**](https://itera.gitbook.io/taikun/user-guide-1/partner/alerting-profiles) if you want to receive a notifications about alerts in your project. Detach if notifications are no longer needed.



### ![](../../../.gitbook/assets/unlock.png)**Lock/**![](<../../../.gitbook/assets/lock (3).png>)**Unlock**

![](<../../../.gitbook/assets/lock (3).png>)Project is unlocked

Clicking the button you lock a project. You can preview some pages (e.g. _Kube Info_), but you can't make any changes in the project (see [Project Details - **Project info**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#project-info)).

​![](../../../.gitbook/assets/unlock.png)Project is locked

Clicking the button you unlock a project and enable action buttons.

****

### **Add Server**

To create a new server click![](<../../../.gitbook/assets/add (1).png>)button and fill all the fields.

You will receive an error message if no flavor has been bound to your project yet. You can also bind the flavor during project creation.

![](https://gblobscdn.gitbook.com/assets%2F-MJQrhtis3vRAM281R7J%2F-MSao7s1LMhb\_HA1Ipuv%2F-MSavIwCCzyPFDmZWaDn%2Fflavor%20info-no%20flavor%20bound.png?alt=media\&token=6e3d912e-509b-42a9-9143-c10d748cca67)

Use the link to bind a flavor.

![Fig. 6: Add Server](<../../../.gitbook/assets/add server (8).gif>)

_Server Name_ - only alphanumeric characters and dash are allowed, 1-30 characters

{% hint style="danger" %}
Letters must be lowercase!
{% endhint %}

_Disk size_ - should be at least 30GB

_Role_ - you are able to choose from several roles for your servers, which are set according to Kubernetes settings

_Flavor_ - choose from the list of offered flavors (e.g. n0.xlarge)

* you can bind the flavors from clouds to the project in [**Flavor Info**](https://itera.gitbook.io/taikun/user-guide-1/partner/flavor-info#bind-to-project)

{% hint style="info" %}
Recommendation for sizing:

* _bastion_ recommended 2 vCPU + 2GB of RAM
* _masters_ recommended 4 vCPU + 8GB of RAM
{% endhint %}

_Number of Servers_ - set number for kubeworker or kubemaster, add odd number of masters (min. 3 for a highly available cluster)

{% hint style="warning" %}
The change **MUST** be committed.
{% endhint %}

_Kubernetes Node Labels_ - label nodes where you want to sent or restrict pods; you can add more labels with add label button, for more info see [Kubernetes docs](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)



For more information see [**Creating a Cluster**](https://itera.gitbook.io/taikun/guidelines/creating-a-cluster).

****

****

**Function buttons**

Between _Project Info_ and _Servers_ are buttons with specific features or more detailed information.



### **Delete**

Delete the selected server/s. You can delete servers to still have a working cluster (1 bastion, 1 master and 1 worker) or delete the whole working cluster.

{% hint style="warning" %}
The change **DOES NOT** have to be committed.
{% endhint %}

****

### **History**

This button will redirect you to Audit Log with pre-filled organization and project, so you can preview the changes made for the chosen project.

![Fig. 7: History](<../../../.gitbook/assets/history (5).gif>)

###

### Kubeconfigs

Add a new kubernetes configuration for your profile and project.

![Fig. 8: Add Kube Config](<../../../.gitbook/assets/kubeconfig (2).png>)

_Kubeconfig Name_ - choose a name for your kubeconfig

_Kubeconfig Role_

* cluster-admin - perform any action on any resource, ClusterRoleBinding - gives full control over every resource in the cluster and in all namespaces (or in very resource in the role binding's namespace - RoleBinding)
* admin - RoleBinding - allows read/write access to most resources in a namespace, does not allow write access to resource quota or to the namespace itself&#x20;
* edit - allows read/write access to most objects in a namespace, does not allow viewing or modifying roles or role bindings, allows accessing Secrets and running Pods as any ServiceAccount in the namespace
* view - see most objects in a namespace, does not allow viewing roles or role bindings, does not allow viewing Secrets

{% hint style="info" %}
For more info, see [kubernetes documentation](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#user-facing-roles).
{% endhint %}

_Application kubeconfig_ - choose if kubeconfig can be used by other users (_all_ or _managers only_) or _Personal kubeconfig_ - kubeconfig can be used only by you



You can see all project's configurations in the table with its _ID_, _Name_, _User_ _Name_, _User_ _Role_, _Project_, _Accessible for all_ and _Actions_.

![Fig. 9: Kubeconfigs](<../../../.gitbook/assets/kubeconfig (3).png>)

#### Actions

![](<../../../.gitbook/assets/download kube config.png>) This .yaml file can be download and use to organize information about clusters, users, namespaces, and authentication mechanisms.

![](<../../../.gitbook/assets/delete (2).png>) Delete your kube config if it is no longer needed. You can also delete _user's_ or _manager's_ kube configs.



### **Kube Info**

If Kubernetes is active, Kube Info button will take you to the Kubernetes configuration. For more see [Projects - **Kubernetes**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/kubernetes).

****

### **Events** <a href="#events" id="events"></a>

You are redirected to **** Events, where you can see all Kubernetes changes made in the project. To preview details for more information to each action use![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MJQrhtis3vRAM281R7J%2F-MNwXBGwTT91-bGRAbAb%2F-MNwbz5QiOnItn3vUmwl%2Fshow.png?alt=media\&token=5311f2d7-e998-4d68-b6dd-019933d28424)button. A green strip indicates a successful action, a brown strip indicates a failed action.​

You can sort Events by:

* _Search_ field
* Filling _Start_ and _End Date_
* Tick _Only failed_ to filter failed actions

![Fig. 10: Events](<../../../.gitbook/assets/events (4).png>)

### Logs <a href="#logs" id="logs"></a>

Preview Kubernetes cluster logs to Grafana.

Logs button is disabled if [**Monitoring is disabled**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#enable-disable-monitoring). To view logs, you must first _Enable Monitoring_.

![Fig. 11: Logs](<../../../.gitbook/assets/logs (3).png>)

Write your query and use _Start date_ and _End Date_ for sorting. You can also expand every message - red is an _added_ action, without color is other log.

![Fig. 12: Logs details](<../../../.gitbook/assets/logs details.png>)

###

### Alerts

First thing when you access Alerts are _Firing Alerts_. This section is refreshed every 5 minutes, but you can also use the refresh button to see the most updated data.

![Fig. 13: Firing alerts](<../../../.gitbook/assets/firing-alerts-refresh+silence (1).gif>)

To see all alerts, use upper right _Show All Alerts_ button. As seen above, firing alerts are marked with red color.

You can _silence_ alert and sort all the alerts by firing, silenced, all or resolved.

Alerts are accessible only if _Monitoring_ is enabled and the project is not empty.

![Fig. 14: Alerts](<../../../.gitbook/assets/firing alert-metrics (2).gif>)

For each alert you can see details and use a link that will redirected you to [**Metrics**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#metrics) **** with the query already filled.

The index number at _Alerts_ shows  the number of firing alerts. ![](<../../../.gitbook/assets/alerts - index number.png>) When the firing alerts are resolved, the number disappears.



Firing alerts also work from the real-time notifications bell in header.&#x20;

![Fig. 15: Alerts bell](<../../../.gitbook/assets/fir alerts notification.gif>)

The notification contains a brief message on a specific project and bellow the message is time of the change. After clicking _Show Project_, you can access the project in which the alert is.

As the name suggests: _Mark as Read_ and _Dismiss all_.



### Metrics

Write a query, search Prometheus Metrics and preview the value needed.

Modify _Step_ or _Date_.

Switch between _Console_ and _Graph_ for better results.

![Fig. 16: Metrics](<../../../.gitbook/assets/metrics (1).gif>)

****

### **Backup Policy**

After you [**Enable Backup**](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#enable-disable-backup), you have to create a _Backup Policy_. After clicking the _Backup Policy ****_ button you get redirected to the new page, where you create a new policy with _Add Policy_ button.

![Fig. 17: Add Policy](<../../../.gitbook/assets/backup policy (1).gif>)

_Name_ - choose a name for your backup (3-30 characters)

_Retention period_ - how long you want to keep the backup (format e.g. 72h)

_Cron period_ - how often you want to do the backup

* predefined - choose from selection from the most common periods
* custom - if you want to specify your own period  (format \* \* \* \* \*)
  *   e.g. every hour - 0 \* \* \* \*; daily - 0 0 \* \* \*, weekly on Sunday - 0 0 \* \* 0

      [crontab guru](https://crontab.guru) with [examples](https://crontab.guru/examples.html)

_Add Include/Exclude Namespace_ - specify the special requests that you  want to include or exclude from  the backup, at least one must be filled

{% hint style="info" %}
The backup is done with a **snapshot method** - backup copy used to create the entire copy of servers every chosen time period.
{% endhint %}

####

There are three tabs:

**Schedules**

In _Schedules_ you can find overview of your backup policy.

![Fig. 18: Schedules](<../../../.gitbook/assets/backup policy - backups (3).png>)

![](../../../.gitbook/assets/detuails.png)_Show description_ - see detailed e.g. specification, metadata etc.

__![](<../../../.gitbook/assets/delete (2).png>)_Delete_ - stop the backup by deleting the policy



**Backups**

_Backups_ contain backups from schedules.

![Fig. 19: Backups](<../../../.gitbook/assets/backup policy - backups (2).png>)

![](../../../.gitbook/assets/detuails.png)_Show description_ - see detailed e.g. specification, metadata etc.

![](<../../../.gitbook/assets/reset vm.png>) _Restore backup_ - if anything goes wrong, you can restore the backup, which you will then see in _Restores_ tab

__![](<../../../.gitbook/assets/delete (2).png>)_Delete_ - delete the backup



**Restores**

Overview of restores from _Backups_.

![Fig. 20: Restores](<../../../.gitbook/assets/backup policy - restores (1).png>)

![](../../../.gitbook/assets/detuails.png)_Show description_ - see detailed e.g. metadata etc.

__![](<../../../.gitbook/assets/delete (2).png>)_Delete_ - delete the restore



### Dashboard

Dashboard is accessible only if cluster is created and [monitoring is enabled](project-details.md#enable-disable-monitoring).

![Fig. 21: Dashboard](<../../../.gitbook/assets/dashboard (5).gif>)

Here you can see graphs with _Memory_ and _CPU_ usage for the project. You can also add **Query** you want.

![Fig. 22: Add Predefined Query](<../../../.gitbook/assets/dashboard - query (1).png>)

_Name_ - choose name for your query (e.g. My Query)

_Expression_ - fill in [_Metrics_](project-details.md#metrics) data (e.g. node\_procs\_running)

_Description_ - describe your query (e.g. Node Process Running)

_Category Name_ - choose category for your query (e.g. Nodes)

