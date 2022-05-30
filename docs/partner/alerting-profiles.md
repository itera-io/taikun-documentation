
# **Alerting Profiles**

*Select organization* for a better overview of Alerting Profiles.

If you want to receive notifications when there is some alert in you project, just set the alerting profile and attach it to the project.


## **Add Alerting Profile**

If you want a new alerting profile, use![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/alerting-profiles/add-alerting-profile-btn.png){: .middle} button.

<figure markdown>
  ![Figure.1: Add Alerting Profile](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/alerting-profiles/add-alerting-profile.png)
  <figcaption>Figure.1: Add Alerting Profile</figcaption>
</figure>

*Organization* - choose from drop-down selection of organizations

*Name* - choose name for your alerting profile

*Slack Configuration* - if you have created a [slack configuration](../slack-configuration), you can use it in profile

*Reminder* - set the reminder for *None*, *HalfHour*, *Hourly*, *Daily*

*E-mails* - receive notifications with e-mail

*Webhooks* - use webhooks for application alert

*Integrations* - set notifications for different apps (Opsgenie, Pagerduty, Splunk and MicrosoftTeams)

## **Alerting Profile overview**

<figure markdown>
  ![Figure.2: Alerting Profiles](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/alerting-profiles/alerting%20profiles.png "Alerting Profiles")
  <figcaption>Figure.2: Alerting Profiles</figcaption>
</figure>


Each Profile is described by *ID*, *Name*, *Organization Name*, *Slack Configuration Name*, *Associated Projects*, *E-mail*, *Webhooks*, *Created By and Actions*.

You can change or add more *E-mails* and *Webhooks*. To each webhooks you can add multiple headers (*Key*, *Value*).

You can extend the table to see the last modification (*Last Modified* and *Last Modified By*).

## **Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/lock.png){: .middle} Un/Lock the profile to dis-/enable it from drop-down selection in project, you cannot lock default profile

:pencil2: Update *Name* or *Slack Configuration*

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete the profile if it is no longer needed, only profiles with no associated projects can be deleted,  you cannot delete default profile


## **Attaching the Profile to the Project**

There are 2 ways to attach your alerting profile to the project:

* [when project is created](../projects/creating-a-new-project) - just check *Add Alerting Profile* during project creation
* [after project is created](../projects/project-details-k8s/#attachdetach-alerting-profile) - use drop-down selection *Actions* in project, click *Attach Alerting Profile* and choose which profile you want to attach to the project


## **Detach Alerting Profile**

Use drop-down selection *Actions* in project, click *Detach Alerting Profile* and choose which profile you want to detach to the project.
