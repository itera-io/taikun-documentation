# Project Details

By clicking the selected project you are redirected to the **Servers**. Here you can see all servers for the project with their description.

![Fig. 1: Accessing Project's details](<../../.gitbook/assets/access project (1).gif>)



### Project Info

Under **Servers** title is a brief description of the project - such as _Project Name ****_ (with locked/unlocked image), _Project_ _Status_, _Cloud_ _Type_, _Kubernetes_ _Version_, _Access Profile_,  _Cloud_ _Credentials_, _Kubernetes_ _Profile_, _Alerting Profile_, _Access IP Address_ (if you use this address to ssh connect, please do not use user ubuntu, it's in use by Taikun for managing the cluster) and _Kubernetes Health_.

![Fig. 2: Project Info](../../.gitbook/assets/label.png)

You can also see here ETC=Estimated Time to Complete. It is approx time (in minutes) until the cluster will be completed.

![ETC](../../.gitbook/assets/etc.png)



### Servers

Every Server is described by _ID_, _Server Name_, _IP Address_, _Flavor_, _CPU/RAM/Disk Size_, _Role_, _Status_, _Kubernetes Health_ and _Creation Time_. If you expand the table, you can see the last modification made (_Last Modified_, _Last Modified By_).

![Fig. 3: Servers for Project](<../../.gitbook/assets/servers (6).png>)

Server status can be:

* Deleting
* Failure
* Pending
* Pending Delete
* Pending Upgrade
* Ready
* Updating
* Upgrading



#### &#x20;**Actions**![](../../.gitbook/assets/actions.png)****

### **Upgrade**

Upgrade your version of Kubespray to the latest one.

The button is disabled, if your Kubernetes are up to date. Also if there was chosen to _Auto Upgrade_ during creation.

### **Commit**

Sends the changes to the repository.

Once the cluster is committed you will see [**ETC**](https://itera.gitbook.io/taikun/user/projects/project-details#project-info) in project info.

### **Repair**

When the server/s are _Failed_ or there is some other problem in the cluster, it can be repaired by changing the status to _Ready_. If all the servers have failed during the first creation, the repair button works as _commit_ and you should use it. If only one server is failed, you should change only the one server's status, because _repair_ will restart the status of all servers.

![Fig.4: Repair](<../../.gitbook/assets/repair (5).gif>)



{% hint style="info" %}
If the project is locked:lock: (which you can see under [**Project Info**](https://itera.gitbook.io/taikun/user-guide-1/user/projects/project-details#project-info)), you can only preview some pages (e.g. _Kube Info_). You can't make any changes.
{% endhint %}



### **Add Server**

To create a new server click![](<../../.gitbook/assets/add server (2).png>)button and fill all the fields. You, as user, can't delete servers - think twice which and how many servers you want to create.

![Fig. 5: Add Server](<../../.gitbook/assets/add workers (2).gif>)

_Server Name_ - only alphanumeric characters and dash are allowed, 1-30 characters

{% hint style="danger" %}
Letters must be lowercase!
{% endhint %}

_Disk size_ - should be **at least** 30GB

_Role_ - you are able to choose from several roles for your servers, which are set according to the Kubernetes settings

_Number of Servers_ - set number for kubeworker or kubemaster, add odd number of masters (min. 3 for a highly available cluster)

{% hint style="warning" %}
The change **MUST** be committed.
{% endhint %}

_Flavor_ - choose from the list of offered flavors (e.g. n0.large)

{% hint style="info" %}
Recommendation for sizing:

* _bastion_ recommended 2 vCPU + 2GB of RAM
* _masters_ recommended 4 vCPU + 8GB of RAM
{% endhint %}

_Kubernetes Node Labels_ - label nodes where you want to sent or restrict pods; you can add more labels with add label button, for more info see [Kubernetes docs](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)

__

**Function buttons**

Between _Project Info_ and _Servers_ are buttons with specific features or more detailed information.

![Fig. 6: Function Buttons](<../../.gitbook/assets/action buttons (15).png>)

### Kubeconfigs

Add a new kubernetes configuration for your profile and project.

![Fig. 7: Add Kubeconfig](<../../.gitbook/assets/add kube config.png>)

_Kubeconfig Name_ - choose a name for your kubeconfig (3-230 characters)

_Kubeconfig Role_

* cluster-admin - perform any action on any resource, ClusterRoleBinding - gives full control over every resource in the cluster and in all namespaces (or in very resource in the role binding's namespace - RoleBinding)
* admin - RoleBinding - allows read/write access to most resources in a namespace, does not allow write access to resource quota or to the namespace itself&#x20;
* edit - allows read/write access to most objects in a namespace, does not allow viewing or modifying roles or role bindings, allows accessing Secrets and running Pods as any ServiceAccount in the namespace
* view - see most objects in a namespace, does not allow viewing roles or role bindings, does not allow viewing Secrets

{% hint style="info" %}
For more info, see[ kubernetes documentation](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#user-facing-roles).
{% endhint %}

_Application/Personal Kubeconfig_ - choose if kubeconfig can be used by other users or only by you

__

You can see all project's configurations in the table with its _ID_, _Name_, _User_ _Name_, _User_ _Role_, _Project_, _Accessible for all_ and _Actions_.

![Fig.8: Kube Configs](<../../.gitbook/assets/kubeconfig (1).png>)

#### Actions

![](../../.gitbook/assets/download.png)This .yaml file can be download and use to organize information about clusters, users, namespaces, and authentication mechanisms.

![](<../../.gitbook/assets/delete (2).png>)Delete your kube config if it is no longer needed.

****

### **Kube Info**

If Kubernetes is active, Kube Info button will take you to the Kubernetes configuration. For more see [Projects - **Kubernetes**](https://itera.gitbook.io/taikun/user-guide-1/user/projects/kubernetes).

### ****

### **Events**

You are redirected to **** Events, where you can see all Kubernetes changes made in the project. To preview details for more information to each action use![](../../.gitbook/assets/show.png)button. A green strip indicates a successful action, a red strip indicates a failed action. Use _Clear events_ for deleting all the events.

You can sort Events by:

* _Search_ field
* Filling _Start_ and _End Date_
* Tick _Only failed_ to filter failed actions

![Fig. 9: Events for Monitoring](<../../.gitbook/assets/events (2).png>)



### Logs

Preview Kubernetes cluster logs to Grafana.

Logs button is disabled if _Monitoring_ is disabled.

![Fig. 10: Logs](<../../.gitbook/assets/logs (3).png>)

Write your query and use _Start date_ and _End Date_ for sorting. You can also expand every message - red is added action, no color is other.

![Fig. 11: Logs details](<../../.gitbook/assets/logs details.png>)



### Alerts

First thing when you access Alerts are _Firing Alerts_. This section is refreshed every 5 minutes, but you can also use the refresh button to see the most updated data.

![Fig. 12: Firing Alerts](<../../.gitbook/assets/firing alert.gif>)

To see all alerts, use upper right _Show All Alerts_ button. As seen above, firing alerts are marked with red color. For each alert you can see details and use a link that will redirected you to [**Metrics**](https://itera.gitbook.io/taikun/user-guide-1/user/projects/project-details#metrics) **** with the query already written.

Alerts are accessible only if _Monitoring_ is enabled and the project is not empty.

![Fig. 13: Alerts](<../../.gitbook/assets/firing alert-metrics.gif>)

The index number at _Alerts_ shows the number of firing alerts. ![](<../../.gitbook/assets/alerts - index number.png>) When the firing alerts are resolved, the number disappears.



Firing alerts also work from the real-time notifications bell in the header. Red ones are indicate alert, green ones means that the alert is resolved.&#x20;

![Fig. 14: Alerts bell](<../../.gitbook/assets/fir alerts.gif>)

The notification contains a brief message on a specific project and bellow the message is time of the change. After clicking _Show Project_, you can access the project in which the alert is.

As the name suggests: _Mark as Read_ and _Dismiss all_.



### Metrics

Write a query, search Prometheus Metrics and preview the value needed.

Modify _Step_ or _Date_.

Switch between _Console_ and _Graph_ for better results.

![Fig. 15: Metrics](<../../.gitbook/assets/metrics (1).gif>)



### Project Dashboard

Dashboard is accessible only if cluster is created and monitoring is enabled.

![Fig. 16: Project Dashboard](<../../.gitbook/assets/dashboard (4).gif>)

Here you can see graphs with _Memory_ and _CPU_ usage for the project. You can also see added Query from [Manager](https://itera.gitbook.io/taikun/manager/projects/project-details#dashboard) or [Partner](https://itera.gitbook.io/taikun/partner/projects/project-details#dashboard).

