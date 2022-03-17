# **Project Details - K8s**

By clicking the selected project or K8s View you are redirected to the **Kubernetes Servers**. Here you can see all K8s servers for the project with their description.

<figure markdown>
  ![Accessing Project's details]( https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/access-k8s-servers.gif "Accessing Project's details - K8s")
  <figcaption>Fig .1: Accessing project's details</figcaption>
</figure>

## **Project Info**

Under **Server**s title is a brief description of the project - such as *Project Name* (with locked/unlocked image), *Project Status*, *Cloud Type*, *Kubernetes Version*, *Access Profile*,* Cloud Credentials*, *Kubernetes Profile*, *Alerting Profile*, *Policy Profile*, *Access IP Address* (if you use this address to ssh connect, please do not use user ubuntu, it's in use by Taikun for managing the cluster) and *Kubernetes Health*.

<figure markdown>
  ![Project Info](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/project-info.png "Project Info")
  <figcaption>Fig .2: Project info</figcaption>
</figure>

You can also see here ETC=Estimated Time to Complete. It is approx time (in minutes) until the cluster will be completed.

<figure markdown>
  ![ETC](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/etc.png "ETC")
  <figcaption>Fig .3: ETC</figcaption>
</figure>

## **Servers**

Every Server is described by *ID*, *Server Name*, *IP Address*, *Flavor*, *CPU/RAM/Disk Size*, *Role*, *Status*, *Kubernetes Health* and *Creation Time*. If you expand the table, you can see the last modification made (*Created By*, *Last Modified*, *Last Modified By*).

<figure markdown>
  ![Servers for Project](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/servers.png "Servers for Project")
  <figcaption>Fig .4: Servers for project</figcaption>
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

## **Actions**

### **Upgrade**

Upgrade your version of Kubespray to the latest one.
The button is disabled, if your Kubernetes are up to date. Also if you checked *Auto Upgrade* during creation.

### **Commit**

Sends the changes to the repository.
Once the cluster is committed you will see **ETC** in project info.

### **Repair**

When the server/s are Failed or there is some other problem in the cluster, use repair button.

<figure markdown>
  ![Repair](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/repair.gif "Repair")
  <figcaption>Fig .5: Repair</figcaption>
</figure>

???+ warning
	If the project is locked:lock: which you can see under [**Project Info**](#project-info), you can only preview some pages (e.g. *Kube Info*). You can't make any changes.

## **Add Server**

To create a new server click![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/add-server-button.png "Add Server"){: .middle} button and fill all the fields. You, as user, **can't** delete servers - think twice which and how many servers you want to create.

<figure markdown>
  ![Add Server](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/add-servers.gif "Add Server")
  <figcaption>Fig .6: Add server</figcaption>
</figure>

*Server Name* - only alphanumeric characters and dash are allowed, 1-30 characters

???+ warning
	Letters must be lowercase!

*Disk size* - should be **at least** 30GB

*Role* - you are able to choose from several roles for your servers, which are set according to the Kubernetes settings

*Number of Servers* - set number for kubeworker or kubemaster, add odd number of masters (min. 3 for a highly available cluster)

???+ warning
	The change **MUST** be committed.

*Flavor* - choose from the list of offered flavors (e.g. n0.large)

???+ info
	Recommendation for sizing:

	* *bastion* recommended 2 vCPU + 2GB of RAM
	* *masters* recommended 4 vCPU + 8GB of RAM


*Kubernetes Node Labels* - label nodes where you want to sent or restrict pods; you can add more labels with add label button, for more info see [Kubernetes docs](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/).

## **Function buttons**

Under *Add Server* are buttons with specific features or more detailed information.

<figure markdown>
  ![Function Buttons](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/function-buttons.png "Function buttons")
  <figcaption>Fig .7: Function buttons</figcaption>
</figure>

### **Kubeconfigs**

Add a new kubernetes configuration for your profile and project.

<figure markdown>
  ![Add Kubeconfig](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/add-kube-config.png "Add Kubeconfig")
  <figcaption>Fig .8: Add kubeconfig</figcaption>
</figure>

*Kubeconfig Name* - choose a name for your kubeconfig (3-230 characters)

*Kubeconfig Role*

* cluster-admin - perform any action on any resource, ClusterRoleBinding - gives full control over every resource in the cluster and in all namespaces (or in very resource in the role binding's namespace - RoleBinding)
* admin - RoleBinding - allows read/write access to most resources in a namespace, does not allow write access to resource quota or to the namespace itself&#x20;
* edit - allows read/write access to most objects in a namespace, does not allow viewing or modifying roles or role bindings, allows accessing Secrets and running Pods as any ServiceAccount in the namespace
* view - see most objects in a namespace, does not allow viewing roles or role bindings, does not allow viewing Secrets

???+ info
	For more info, see [kubernetes documentation](https://kubernetes.io/docs/reference/access-authn-authz/rbac/#user-facing-roles).

*Personal Kubeconfig* - kubeconfig can be used only by you

You can see all project's configurations in the table with its *ID*, *Name*, *User Name*, *User Role*, *Project*, *Accessible for all*, *Konfig Role Name*, *Created By*  and Actions.

<figure markdown>
  ![Kube Configs](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/kubeconfig.png "Kubeconfigs")
  <figcaption>Fig .9: Kube configs</figcaption>
</figure>

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/download.png "Download"){: .middle} This .yaml file can be download and use to organize information about clusters, users, namespaces, and authentication mechanisms.

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "Delete"){: .middle} Delete your kube config if it is no longer needed.

### **K8s Info**

If Kubernetes is active, Kube Info button will take you to the Kubernetes configuration. For more see [**Projects - Kubernetes**](../kubernetes).

### **Events**

You are redirected to Events, where you can see all Kubernetes changes made in the project. To preview details for more information to each action use![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show.png)button. A green strip indicates a successful action, a red strip indicates a failed action. Use *Clear events* for deleting all the events.

You can sort Events by:

* *Search* field
* Filling *Start* and *End Date*
* Tick *Only failed* to filter failed actions

<figure markdown>
  ![Events for Monitoring](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/events.png "Events for monitoring")
  <figcaption>Fig .10: Events for monitoring</figcaption>
</figure>

### **Logs**

Preview Kubernetes cluster logs to Grafana.
Logs button is disabled if *Monitoring* is disabled.

<figure markdown>
  ![Logs](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/logs.png "Logs")
  <figcaption>Fig .11: Logs</figcaption>
</figure>

Write your query and use *Start date* and *End Date* for sorting. You can also expand every message - red is added action, no color is other.

<figure markdown>
  ![Logs details](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/logs-details.png "Logs details")
  <figcaption>Fig .12: Logs details</figcaption>
</figure>

### **Alerts**

First thing when you access Alerts are *Firing Alerts*. This section is refreshed every 5 minutes, but you can also use the refresh button to see the most updated data.

<figure markdown>
  ![Firing Alerts](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/firing-alerts.gif "Firing alerts")
  <figcaption>Fig .13: Firing alerts</figcaption>
</figure>

To see all alerts, use upper right *Show All Alerts* button. As seen above, firing alerts are marked with red color. For each alert you can see details and use a link that will redirected you to [**Metrics**](#metrics) with the query already written.

Alerts are accessible only if *Monitoring* is enabled and the project is not empty.

<figure markdown>
  ![Alerts](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/firing-alert-metrics.gif "Alerts to Metrics")
  <figcaption>Fig .14: Alerts</figcaption>
</figure>

The index number at *Alerts* shows the number of firing alerts. ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/alerts-index-number.png){: .middle} When the firing alerts are resolved, the number disappears.

Firing alerts also work from the real-time notifications bell in the header. Red ones are indicate alert, green ones means that the alert is resolved.

<figure markdown>
  ![Alerts bell](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/firing-alerts-bell.gif "Alerts Bells")
  <figcaption>Fig .15: Alerts bell</figcaption>
</figure>

The notification contains a brief message on a specific project and bellow the message is time of the change. After clicking *Show Project*, you can access the project in which the alert is.

As the name suggests: *Mark as Read* and *Dismiss all*.

### **Metrics**

Write a query, search Prometheus Metrics and preview the value needed.
Modify *Step* or *Date*.

Switch between *Console* and *Graph* for better results.

<figure markdown>
  ![Metrics](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/metrics.gif "Metrics")
  <figcaption>Fig .16: Metrics</figcaption>
</figure>

### **Project Dashboard**

Dashboard is accessible only if cluster is created and *monitoring* is enabled.

<figure markdown>
  ![Project Dashboard](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/user/projects/project-details/dashboard.gif "Project Dashboard")
  <figcaption>Fig .17: Metrics</figcaption>
</figure>

Here you can see graphs with *Memory* and *CPU* usage for the project. You can also see added Query from [Manager](../../../manager/projects/project-details-k8s#dashboard) or [Partner](../../../partner/projects/project-details-k8s#dashboard).
