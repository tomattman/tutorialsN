---
title: BUG 1803 update yaml 123456
description: The following steps will explain how to create a basic Java project to call OData services using the SAP S/4HANA Cloud SDK on Cloud Foundry.
tags: [ tutorial>intermediate, products>sap-s-4hana-cloud-sdk, tutorial>license]
primary_tag: products>sap-s-4hana-cloud-sdk
time: 220
---

[ACCORDION-BEGIN [Step 5: ](Deploying the Project)]

```yaml
invoice: 34843
date   : 2001-01-23
bill-to: &id001
    given  : Chris
    family : Dumars
    address:
        lines: |
            458 Walkman Dr.
            Suite #292
        city    : Royal Oak
        state   : MI
        postal  : 48046
ship-to: *id001
product:
    - sku         : BL394D
      quantity    : 4
      description : Basketball
      price       : 450.00
    - sku         : BL4438H
      quantity    : 1
      description : Super Hoop
      price       : 2392.00
tax  : 251.42
total: 4443.52
comments: >
    Late afternoon is best.
    Backup contact is Nancy
    Billsmer @ 338-4338.
    
```
[DONE]

[ACCORDION-END]

---
