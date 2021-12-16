---
description: Create and Manage Rules
---

# Billing Rules

Create a Rule, [assign](https://itera.gitbook.io/taikun/user-guide-1/partner/organizations#actions) it to the organization and see the result in [**Chargeback**](https://itera.gitbook.io/taikun/user-guide-1/partner/chargeback).

![Fig. 1: Billing Rules](<../.gitbook/assets/billing rules (3).png>)

**Rules** can be sorted by _Name_, _Metric Name_, _Created_ and _Type_.

By clicking arrow > you can expand the table to see _Created By_, _Last Modified_ and _Last Modified By_.



### New Rule

To create Rule use ![](<../.gitbook/assets/add rule (1).png>) button.

![Fig. 1: Add Rule](<../.gitbook/assets/add rule (2).png>)

_Name_ - Rule name

_Metric Name_ - exact metric name from Prometheus (e.g. volumes, flavor, networks) you want to bill, if you select _Billing credentials_ first, you can choose from drop-down selection (wit autocomplete)

_Bind rule to organization_ - assign rule to selected organization or choose none and bind it later

_Billing Credentials_ - drop-down of operation credentials

_Type_ - drop-down: Count (calculate package as unit - e.g. flavors) or Sum (calculate per quantity - e.g. GBs)

_Price_ - billing in CZK per selected unit

_Price Rate_ - in percents (0-1000 %), 100 equals one

_Add Label_ - The label indicates the variable name (_Label_) and value of the label (_Label Value_), see the **Table 1** below

**Table 1: Labels in Billing Rules**

| Label             | Label Value |
| ----------------- | ----------- |
| Flavor            | n0.xmedium  |
| taikun\_org\_name | itera       |
| taikun\_org\_id   | 2           |

{% hint style="warning" %}
Once you bind the organization the cron job starts to calculate. The billing starts at the beginning of every hour and once it's bound to organization, it can't be paused.
{% endhint %}



### Actions

Change the properties of the rule.

####

#### ![](../.gitbook/assets/panelak.png)Bound Organizations

Select the organization you want to assign the rule and then click the assign button. If you choose a new organization the billing starts from the beginning of next hour.



#### :pencil2:Edit Prometheus Info

Update the rule and change the parameters.



#### ![](../.gitbook/assets/copy.png)Copy Rule

When creating similar rule, when you want to change just one or few parameters, you can use copy button - window with copied parameters will pop-up.



#### ![](../.gitbook/assets/delete.png)Delete

Delete the rule if no longer needed.
