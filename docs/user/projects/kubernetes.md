# Kubernetes

To access **Kubernetes** go to Projects - Servers - _Kube Info_ or use the K8's button![](../../.gitbook/assets/kubernetes-active.png)in _Projects_.

![Fig. 1: Access Kubernetes](<../../.gitbook/assets/access kubernetes (1).gif>)



In **Kubernetes** tab can be found:

* **Nodes**
  * _Message_, _Reason_, _Status_ and _Type_
* **Deamon** **Set**
  * _Namespace_, _Name_, _Status_ and _Age_
* **Persistent Volume Claim**
  * _Namespace_, _Name_, _Phase_, _Size_, _Storage_ _Class_ _Name_ and _Age_
* **Deployment**
  * _Namespace_, _Name_, _Status_ and _Age_
* **Config Map**
  * _Namespace_, _Name_ and _Age_
* **Secret**
  * _Namespace_, _Name_ and _Age_
* **Sts**
  * _Namespace_, _Name_, _Status_ and _Age_
* **Service\***
  * _Namespace_, _Name_, _Type, External IP_ and _Age_
* **Pods**
  * _Namespace_, _Name_, _Node_ _Name_, _Age_, _Status_, _Restart_ _Count_, _Kill_ _Pod_, _Terminal_ and _Logs_
* **Ingress**
  * _Namespace_, _Name_, _Hosts_ and _Age_
* **Ingress**
  * _Namespace_, _Name_, _Hosts_ and _Age_
* **CRD** (Custom Resource Definition)
  * _Name_, _Group, List Kind, Spec name kind, Labels_ and _Age_
* **PDB** (Pod Disruption Budgets)
  * _Namespace_, _Name_ and _Created At_

{% hint style="danger" %}
\*Please do NOT deploy any apps in monitoring **Service**, because Taikun uses the monitoring namespace heavily! And if you disable the monitoring, all pvc in monitoring will be deleted.
{% endhint %}



![Fig. 2: Kubernetes](<../../.gitbook/assets/kubernetes - overview.gif>)

You can use sort buttons or search button in each section for easier searching.

{% hint style="info" %}
Except **Pods** tab are __ all tabs for preview only.
{% endhint %}



#### Actions

![](../../.gitbook/assets/detuails.png) Show description - for all tabs except _Nodes_

__

### Pods

#### Kill Pod

**Pod** can be killed with Kill Pod![](<../../.gitbook/assets/kill pod (1).png>)button.

#### Terminal

Open **Terminal** to control your container/s.

![Fig. 3: Terminal](<../../.gitbook/assets/kubernetes - terminal.gif>)

#### Logs

Logs record events happening in cluster. You can check the logs for more details. To search the logs visit [**Projects** - Project Details - Logs](https://itera.gitbook.io/taikun/user-guide-1/user/projects/project-details#logs).

![Fig. 4: Logs](../../.gitbook/assets/kubernetes-logs.gif)
