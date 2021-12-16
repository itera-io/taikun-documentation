---
description: Set your rule for showback
---

# Showback Rules

_Select organization_ for a better overview of Access Profiles.

When visiting the tab first you see overview of Showback Rules.

![Fig. 1: Showback Rules overviews](<../.gitbook/assets/showback rules (1).png>)

Every showback rule is described by _ID_, _Name_, _Metric_ _Name_, _Organization_, _Labels_ (if there is any), _Kind_, _Type_, _Global_ _alert_ _limit_, _Project_ _alert_ _limit_, _Price_, _Showback credentials_ (if there is any), date and time _Created_ and _Actions_.



#### Actions

![](../.gitbook/assets/edit.png)Edit Showback Rule - change parameters of your rule

![](<../.gitbook/assets/copy (2).png>)Copy Showback Rule - if you want to create similar rule, you can copy existing one, don't forget to change rule name

![](<../.gitbook/assets/delete (2).png>)Delete Rule - if you want to stop the rule, simply delete it



### Add Rule

Create a new showback rule for your organization.

![Fig. 2: Add Showback Rule](<../.gitbook/assets/add showback rule.png>)

_Organization_ - choose organization

_Name_ - choose name for your rule

_Metric Name_ - use valid metric, you can use [**Metrics**](https://itera.gitbook.io/taikun/partner/projects/project-details#metrics) for examples

_Kind_ - choose kind for the rule

* General - data source is taikun
* External - data source is external - you need to change Showback Credentials

_Type_ - drop-down: Count (calculate package as unit - e.g. flavors) or Sum (calculate per quantity - e.g. GBs)

_Price_ - billing in CZK per selected unit

_Project Alert Limit_ - set limit of alerts for one project

_Global Alert Limit_ - set limit of alerts for all projects

_Showback Credentials_ - drop-down of operation credentials

_Labels_ - the label indicates the variable name (_Label_) and value of the label (_Label Value_), see examples in the **Table 1** below

**Table 1: Labels in Showback Rules**

| Label             | Label Value |
| ----------------- | ----------- |
| Flavor            | n0.xmedium  |
| taikun\_org\_name | itera       |
| taikun\_org\_id   | 2           |

{% hint style="warning" %}
Once you add the rule the cron job starts to calculate. The price for showback summary starts at the beginning of every hour and it can't be paused. Rule is stopped by deleting it.
{% endhint %}
