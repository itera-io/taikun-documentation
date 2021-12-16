---
description: How to install LoadBalancers to your Cluster
---

# LoadBalancers

{% hint style="warning" %}
LoadBalancing Flavor should have at least:

* 1GB RAM
* 1 vCPU
{% endhint %}



### Prepare the configuration file _prod.yaml_

```
yaml:
  tenantName: "kubernetes"
  clusterName: "<cluster_name>"
  subnetId: "<kubernetes_subnet_id>"
  flavorId: "<flavorId_for_loadbalancing_instances>"
  publicKey: "<public_key_matching_the_ssh_key_below>"
  floatingNetworkId: "<floating_network_id_for_loadbalancing>"
  identityEndpoint: "<openstack_identity_endpoint>"
  userName:         "<openstack_username>>"
  password:         "<openstack_password>"
  domainName: "default"
  keepalivedRouterIdRange: "1-255"
ssh_key: |
  SSH_PRIVATE_KEY
```



### Add Itera Helm Chart Repository

`helm repo add itera https://repo.itera.io/repository/itera --kubeconfig=admin.conf`

```
WARNING: Kubernetes configuration file is group-readable. This is insecure. Location: admin.conf
WARNING: Kubernetes configuration file is world-readable. This is insecure. Location: admin.conf
"itera" has been added to your repositories
```



### Install _taikun-lb_ using _helm_

{% hint style="danger" %}
_taikun-lb_ is only available for **OpenStack** with **Octavia disabled**. You need to add image [https://repo.itera.io/repository/images/taikun-lb.qcow2](https://repo.itera.io/repository/images/taikun-lb.qcow2) to OpenStack with **tag** "taikun-lb".

Command to add an image to OpenStack:

`openstack image create --disk-format qcow2 --container-format bare --private  --file taikun-lb.qcow2 --tag taikun-lb --property hw_disk_bus=scsi --property hw_scsi_model=virtio-scsi taikun-lb`
{% endhint %}



`helm upgrade --install itera-lb -f prod.yaml --namespace=kube-system itera/taikun-lb --kubeconfig=admin.conf`

```
WARNING: Kubernetes configuration file is group-readable. This is insecure. Location: admin.conf
WARNING: Kubernetes configuration file is world-readable. This is insecure. Location: admin.conf
Release "itera-lb" has been upgraded. Happy Helming!
NAME: itera-lb
LAST DEPLOYED: Thu Mar  4 11:28:31 2021
NAMESPACE: default
STATUS: deployedInfrastructure removal

REVISION: 4
TEST SUITE: None
```



### Check _taikun-lb_ is installed

`export KUBECONFIG=admin.conf; kubectl get pod`

```
NAME                                   READY   STATUS             RESTARTS   AGE
itera-lb-deployment-69c44bb45c-wtwgm   1/1     Running            0          38m
```



### Install a test application (in this case _wordpress_ from bitnami)

`helm install test-lb bitnami/wordpress --kubeconfig=admin.conf`



### Wait for the service to get a floating IP assigned

`kubectl get svc test-lb-wordpress`

```
NAME                TYPE           CLUSTER-IP      EXTERNAL-IP   PORT(S)                      AGE
test-lb-wordpress   LoadBalancer   10.233.55.232   10.3.228.10   80:30634/TCP,443:31760/TCP   2m27s
```



To enable proxy service for the service, add the following annotation to the service:

```
loadbalancer.taikun.cloud/proxy-protocol: "true"
```



This is the way to restrict which IP has access to the service (https://www.haproxy.com/blog/haproxy/proxy-protocol/) for example:

```
apiVersion: v1
kind: Service
metadata:
  annotations:
    loadbalancer.taikun.cloud/proxy-protocol: "true"
    meta.helm.sh/release-name: test-lb
    meta.helm.sh/release-namespace: default
...
```
