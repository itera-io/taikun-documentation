---
description: Set the notification from Taikun to your Slack
---

# Slack Configurations

You can receive all the changes made from your Taikun organization into Slack channel you choose.

![Fig. 1: Slack configurations](<../.gitbook/assets/slack (3).png>)

###

### Add Slack Config

First you need to set your [_**webhooks**_](https://slack.com/intl/en-cz/help/articles/115005265063-Incoming-webhooks-for-Slack) for Slack and create channel in Slack, where you want to receive notifications.

![Fig. 2: Add Slack Config](<../.gitbook/assets/add slack (3).png>)

_Organization_ - choose organization to which you want to add slack

_Name_ - choose name for your config

_URL_ - insert _**webhook**_ URL from Slack app

_Channel_ - Slack channel for notifications

_Type_ - Alert (receive only alert-type of notification) or General (receive all notifications)



**Successful installation**

Now you will receive notifications in Slack channel for the projects.

![Fig. 3: Slack](<../.gitbook/assets/slack app.png>)

{% hint style="info" %}
The project name in message has link, which will redirect you right to Taikun to the project.
{% endhint %}
