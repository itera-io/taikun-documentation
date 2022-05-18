---
tags:
  - Partner
  - Policy Profiles
hide:
  - tags
---

# **Policy Profiles**

Profile uses [**OPA**](https://www.openpolicyagent.org) (Open Policy Agent) to centralize operational, security, and compliance.

*Select organization* for a better overview of Alerting Profiles.

Accessing the page you can see the overview of all created profiles with selected rules and associated projects.

<figure markdown>
  ![Fig. 1: Policy Profiles](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/policy-profiles/policy-profiles.png "Policy Profiles")
  <figcaption>Fig. 1: Policy Profiles</figcaption>
</figure>


Each profile can be:

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle}/![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/unlock.png){: .middle} Un/lock profile - if you lock the profiles, you can't use them for new Project, edit or delete them

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete - delete non-used and unlocked profiles

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/edit.png){: .middle} Update Profile - update policy profile

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/make-default.png){: .middle} Make default - choose profile which will be then filled during project creation, lighter color indicates selected credentials


## **Add Policy Profile**

<figure markdown>
  ![Fig. 2: Add Policy Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/policy-profiles/add-policy-profile.png)
  <figcaption>Fig. 2: Add Policy Profile</figcaption>
</figure>

*Name* - choose name for the profile

**Features:**

*Forbid NodePort*

*Forbid http ingresses*

*Require Probe*

**Add:**

*Allowed Repositories*

*Forbid Specific Tags*

*Ingress Whitelist*


## **Add Profile to the Project**

You can add the profile during project creation - choosing from drop down selection.

<figure markdown>
  ![Fig. 3: Add Policy during Project creation](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/policy-profiles/add-pp%20project%20creation.png)
  <figcaption>Fig. 3: Add Policy during Project creation</figcaption>
</figure>

Enforce Policies after the project is created. You can disable it the same way.

<figure markdown>
  ![Fig. 4: Add Policy after Project is created](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/policy-profiles/enforce-policy.gif)
  <figcaption>Fig. 4: Add Policy after Project is created</figcaption>
</figure>


???+ warning
    Please keep in mind that namespaces *monitoring*, *velero* and *kube-system* **violate** these policies.
