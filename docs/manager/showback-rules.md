---
tags:
  - Manager
  - Showback-Rules
hide:
  - tags
---

# **Showback Rules**

When visiting the tab first you see overview of Showback Rules.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/showback-rules/showback-rules.png "Showback Rules")
  <figcaption>Fig .1: Showback rules overviews</figcaption>
</figure>

Every showback rule is described by *ID*, *Name*, *Metric Name*, *Organization*, *Labels* (if there is any), *Kind*, *Type*, *Global alert limit*, *Project alert limit*, *Price*, *Showback credentials* (if there is any), date and time *Created* and *Actions*.

## **Add Rule**

Create a new showback rule for your organization.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/showback-rules/add-showback-rule.png "Add Showback Rule")
  <figcaption>Fig .2: Add showback rule</figcaption>
</figure>

*Name* - choose name for your rule

*Metric Name* - use valid metric, you can use [**Metrics**](../projects/project-details-k8s/#metrics) for examples

*Kind* - choose kind for the rule

* General - data source is taikun
* External - data source is external - you need to change Showback Credentials

*Type* - drop-down: Count (calculate package as unit - e.g. flavors) or Sum (calculate per quantity - e.g. GBs)

*Price* - billing in CZK per selected unit

*Project Alert Limit* - set limit of alerts for one project

*Global Alert Limit* - set limit of alerts for all projects

*Showback Credentials* - drop-down of operation credentials

*Labels* - the label indicates the variable name (*Label*) and value of the label (*Label Value*), see examples in the **Table 1** below

**Table 1: Labels in Showback Rules**

| Label             | Label Value |
| ----------------- | ----------- |
| Flavor            | n0.xmedium  |
| taikun\_org\_name | itera       |
| taikun\_org\_id   | 2           |

???+ warning
    Once you add the rule the cron job starts to calculate. The price for showback summary starts at the beginning of every hour and it can't be paused. Rule is stopped by deleting it.

**Actions**

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/edit.png){: .middle} Edit Showback Rule - change parameters of your rule

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/copy.png){: .middle} Copy Showback Rule - if you want to create similar rule, you can copy existing one, don't forget to change rule name

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete Rule - if you want to stop the rule, simply delete it
