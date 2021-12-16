# Create a New Project

If you want to add a new project, use the upper right button![](<../../.gitbook/assets/add (4).png>)in **Projects** tab.

![Fig.1: Add Project](<../../.gitbook/assets/add project (11).gif>)

_Project Name_ - fill in your project name (only alphanumeric lowercase characters and dash are allowed, 3-30 characters; **not** underscore; e.g. my-project1)

_Cloud_ - choose where you want to store your Project, create a new Cloud in [**Cloud Credentials**](https://itera.gitbook.io/taikun/user-guide-1/manager/cloud-credentials)

_Access Profile_ - choose profile which can access the project, create a new profile in [**Access Profiles**](https://itera.gitbook.io/taikun/user-guide-1/manager/access-profiles)

_Alerting Profile_ - if you have created profile in [**Alerting Profiles**](https://itera.gitbook.io/taikun/user-guide-1/manager/alerting-profiles), you can choose it from the drop-down selection

_Kubernetes Profile_ - first create a new profile in [**Kubernetes Profiles**](https://itera.gitbook.io/taikun/user-guide-1/manager/kubernetes-profiles) and than choose from drop down selection

* for openstack: if you choose profile with enabled Taikun Load Balancer, you also have to fill in _Taikun Load Balancer Flavor_, _Router Id Start Range_ and _Router Id End Range_

_Enable Auto Upgrade_ - Kubespray version will be automatically upgraded if new version is available

_Enable Monitoring_ - monitoring a Kubernetes cluster allows easy management of containerized infrastructure by tracking utilization of cluster resources including memory, CPU, and storage

_Enable Backup_ - choose credentials, you can create a new one in [**Backup Credentials**](https://itera.gitbook.io/taikun/user-guide-1/manager/backup-credentials)**.** If you choose not to enable it, you can change it later, see [Projects - Project details - **Backup**](https://itera.gitbook.io/taikun/user-guide-1/manager/projects/project-details#enable-disable-backup)****

_Add Expiration Date_ - set project durability, by default it is set to infinity. After the expiration date, your project is **NOT** affected, deleted or lock. It will stays the same.

_Add Flavor_ - bind the flavor to the project, you can bind more than one flavor and un/bind them later in [**Flavor Info**](https://itera.gitbook.io/taikun/user-guide-1/manager/flavor-info)****
