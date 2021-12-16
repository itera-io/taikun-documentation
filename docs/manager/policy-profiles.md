---
description: Automatically enforce, monitor, and remediate policies
---

# Policy Profiles

Profile uses [**OPA**](https://www.openpolicyagent.org) (Open Policy Agent) to centralize operational, security, and compliance.



Accessing the page you can see the overview of all created profiles with selected rules and associated projects.

![Fig. 1: Policy Profiles](<../.gitbook/assets/policy profiles (1).png>)

Each profile can be:

![](<../.gitbook/assets/lock (3).png>)/![](../.gitbook/assets/unlock.png) Un/lock profile - if you lock the profiles, you can't use them for new Project, edit or delete them

![](<../.gitbook/assets/delete (2).png>) Delete - delete non-used and unlocked profiles

![](../.gitbook/assets/edit.png)Update Profile - update policy profile

![](<../.gitbook/assets/make default.png>)Make default - choose profile which will be then filled during project creation, lighter color indicates selected credentials



### Add Policy Profile

![Fig. 2: Add Policy Profile](<../.gitbook/assets/add policy profile.png>)

_Name_ - choose name for the profile

**Features:**

_Forbid NodePort_

_Forbid http ingresses_

_Require Probe_

**Add:**

_Allowed Repositories_

_Forbid Specific Tags_

_Ingress Whitelist_

__

### Add Profile to the Project

You can add the profile during project creation - choosing from drop down selection.

![Fig. 3: Add Policy during Project creation](<../.gitbook/assets/add project - policy.png>)

Enforce Policies after the project is created. You can disable it the same way.

![Fig. 4: Add Policy after Project is created](<../.gitbook/assets/enforce policy.gif>)



{% hint style="warning" %}
Please keep in mind that namespaces _monitoring_, _velero_ and _kube-system_ **violate** these policies.
{% endhint %}
