---
tags:
  - Manager
  - Kubernetes
hide:
  - tags
---

# **Kubernetes**

To access **Kubernetes** go to Projects - Servers - *K8s Info* or use the K8s button![](ihttps://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/kubernetes.png "K8s") in *Projects*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/kubernetes/access-kuberentes.gif "Access Kubernetes")
  <figcaption>Fig .1: Access Kubernetes</figcaption>
</figure>

In **Kubernetes** tab can be found:

* **Nodes**
    * *Message*, *Reason*, *Status* and *Type*
* **Deamon Set**
    * *Namespace*, *Name*, *Status* and *Age*
* **Persistent Volume Claim**
    * *Namespace*, *Name*, *Phase*, *Size*, *Storage* *Class* *Name* and *Age*
* **Deployment**
    * *Namespace*, *Name*, *Status* and *Age*
* **Config Map**
    * *Namespace*, *Name* and *Age*
* **Secret**
    * *Namespace*, *Name* and *Age*
* **Sts**
    * *Namespace*, *Name*, *Status* and *Age*
* __Service *__
    * *Namespace*, *Name*, *Type*, *External IP* and *Age*
* **Pods**
    * *Namespace*, *Name*, *Node* *Name*, *Age*, *Status*, *Restart* *Count*, *Kill* *Pod*, *Terminal* and *Logs*
* **Ingress**
    * *Namespace*, *Name*, *Hosts* and *Age*
* **Ingress**
    * *Namespace*, *Name*, *Hosts* and *Age*
* **CRD** (Custom Resource Definition)
    * *Name*, *Group*, *List Kind*, *Spec name kind*, *Labels* and *Age*
* **PDB** (Pod Disruption Budgets)
    * *Namespace*, *Name* and *Created At*

???+ warning
    \*Please do NOT deploy any apps in monitoring **Service**, because Taikun uses the monitoring namespace heavily! And if you disable the monitoring, all pvc in monitoring will be deleted.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/kubernetes/k8s.gif "Kubernetes")
  <figcaption>Fig .2: Kubernetes</figcaption>
</figure>

You can use sort buttons or search button in each section for easier searching.

???+ info
    Except **Pods** tab are all tabs for preview only.

### **Actions**

![Show description](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/show-description.png){: .middle} Show description - for all tabs except *Nodes*

## **Pods**

### **Kill Pod**

**Pod** can be killed with Kill Pod![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/kill-pod.png){: .middle} button.

### **Terminal**

Open **Terminal** to control your container's.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/kubernetes/kubernetes-terminal.gif "Terminal")
  <figcaption>Fig .3: Terminal</figcaption>
</figure>

### **Logs**

Logs record events happening in cluster. You can check the logs for more details. To search the logs visit [**Projects - Project Details - Logs**](../project-details-k8s/#logs).

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/projects/kubernetes/kubernetes-logs.gif "Logs")
  <figcaption>Fig .4: Logs</figcaption>
</figure>
