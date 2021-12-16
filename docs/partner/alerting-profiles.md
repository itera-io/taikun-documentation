---
description: Create and Attach Profile to a Project
---

# Alerting Profiles

_Select organization_ for a better overview of Alerting Profiles.

If you want to receive notifications when there is some alert in you project, just set the alerting profile and attach it to the project.



### Add Alerting Profile

If you want a new alerting profile, use![](<../.gitbook/assets/add alerting profile.png>)button.

![Fig. 1: Add Alerting Profile](<../.gitbook/assets/add al prof (2).png>)

_Organization_ - choose from drop-down selection of organizations

_Name_ - choose name for your alerting profile

_Slack Configuration_ - if you have created a [slack configuration](https://itera.gitbook.io/taikun/partner/slack-configuration), you can use it in profile

_Reminder_ - set the reminder for _None_, _HalfHour_, _Hourly_, _Daily_

_E-mails_ - receive notifications with e-mail

_Webhooks_ - use webhooks for application alert

_Integrations_ - set notifications for different apps (Opsgenie, Pagerduty, Splunk and MicrosoftTeams)



### Alerting Profile overview

![Fig. 2: Alerting Profiles](<../.gitbook/assets/alerting profiles (1).png>)

Each Profile is described by _ID_, _Name_, _Organization_ _Name_, _Slack_ _Configuration_ _Name_, _Associated_ _Projects_, _E-mail_, _Webhooks_, _Created_ _By_ and _Actions_.

You can change or add more _E-mails_ and _Webhooks_. To each webhooks you can add multiple headers (_Key, Value_).

You can extend the table to see the last modification (_Last Modified_ and _Last Modified By_).



### Actions

![](<../.gitbook/assets/lock (3).png>)Un/Lock the profile to dis-/enable it from drop-down selection in project, you cannot lock default profile

:pencil2: Update _Name_ or _Slack Configuration_

![](<../.gitbook/assets/delete (2).png>)Delete the profile if it is no longer needed, only profiles with no associated projects can be deleted,  you cannot delete default profile



### Attaching the Profile to the Project

There are 2 ways to attach your alerting profile to the project:

* [when project is created](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/creating-a-new-project) - just check _Add Alerting Profile_ during project creation
* [after project is created](https://itera.gitbook.io/taikun/user-guide-1/partner/projects/project-details#attach-detach-alerting-profile) - use drop-down selection _Actions_ in project, click _Attach Alerting Profile_ and choose which profile you want to attach to the project



### Detach Alerting Profile

Use drop-down selection _Actions_ in project, click _Detach Alerting Profile_ and choose which profile you want to detach to the project.
