
# **Billing Rules**

Create a Rule, [assign](../organizations#actions) it to the organization and see the result in [**Chargeback**](../chargeback).

<figure markdown>
  ![Figure.1: Billing Rules](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/billing-rules/billing-rules.png "Billing Rules")
  <figcaption> Figure.1: Billing Rules </figcaption>
</figure>

**Rules** can be sorted by *Name*, *Metric Name*, *Created* and *Type*.

By clicking arrow > you can expand the table to see *Created By*, *Last Modified* and *Last Modified By*.

### New Rule

To create Rule use ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/billing-rules/add-rule-btn.png){: .middle} button.

<figure markdown>
  ![Figure.2: Add Rule](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/billing-rules/add-rule.png)
  <figcaption> Figure.2: Add Rule </figcaption>
</figure>

*Name* - Rule name

*Metric Name* - exact metric name from Prometheus (e.g. volumes, flavor, networks) you want to bill, if you select *Billing credentials* first, you can choose from drop-down selection (wit autocomplete)

*Bind rule to organization* - assign rule to selected organization or choose none and bind it later

*Billing Credentials* - drop-down of operation credentials

*Type* - drop-down: Count (calculate package as unit - e.g. flavors) or Sum (calculate per quantity - e.g. GBs)

*Price* - billing in CZK per selected unit

*Price Rate* - in percents (0-1000 %), 100 equals one

*Add Label* - The label indicates the variable name (*Label*) and value of the label (*Label Value*), see the **Table 1** below

**Table 1: Labels in Billing Rules**

| Label             | Label Value |
| ----------------- | ----------- |
| Flavor            | n0.xmedium  |
| taikun\_org\_name | itera       |
| taikun\_org\_id   | 2           |

???+ warning
    Once you bind the organization the cron job starts to calculate. The billing starts at the beginning of every hour and once it's bound to organization, it can't be paused.


### Actions

Change the properties of the rule.

#### ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/billing-rules/panelak.png){: .middle} Bound Organizations

Select the organization you want to assign the rule and then click the assign button. If you choose a new organization the billing starts from the beginning of next hour.


#### :pencil2:  Edit Prometheus Info

Update the rule and change the parameters.


#### ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/copy.png){: .middle} Copy Rule

When creating similar rule, when you want to change just one or few parameters, you can use copy button - window with copied parameters will pop-up.


#### ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete

Delete the rule if no longer needed.
