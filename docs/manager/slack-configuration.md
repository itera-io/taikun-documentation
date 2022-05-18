---
tags:
  - Manager
  - Slack-Configuration
hide:
  - tags
---

# **Slack Configurations**

You can receive all the changes made from your Taikun organization into Slack channel you choose.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/slack/slack.png "Slack configurations")
  <figcaption>Fig .1: Slack configuration</figcaption>
</figure>

## **Add Slack Config**

First you need to set your [**webhooks**](https://slack.com/intl/en-cz/help/articles/115005265063-Incoming-webhooks-for-Slack) for Slack and create channel in Slack, where you want to receive notifications.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/slack/add-slack.png "Add Slack")
  <figcaption>Fig .2: Add slack config</figcaption>
</figure>

*Name* - choose name for your config

*URL* - insert ***webhook*** URL from Slack app

*Channel* - Slack channel for notifications

*Type* - Alert (receive only alert-type of notification) or General (receive all notifications)


**Successful installation**

Now you will receive notifications in Slack channel for the projects.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/slack/slack-app.png "Slack")
  <figcaption>Fig .3: Slack</figcaption>
</figure>

???+ info
    The project name in message has link, which will redirect you right to Taikun to the project.
