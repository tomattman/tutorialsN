---
title: BUG 1803 update yaml 2
description: The following steps will explain how to create a basic Java project to call OData services using the SAP S/4HANA Cloud SDK on Cloud Foundry.
tags: [ tutorial>intermediate, products>sap-s-4hana-cloud-sdk]
primary_tag: products>sap-s-4hana-cloud-sdk
time: 20
---

[ACCORDION-BEGIN [Step 5: ](Deploying the Project)]

```YAML

    "yaml.customTags": [
    "!Scalar-example scalar",
    "!Seq-example sequence",
    "!Mapping-example mapping"
]

item:
  - method: UPDATE
    where: &FREE_ITEMS
      - Portable Hole
      - Light Feather
    SellPrice: 0
    BuyPrice: 0

npc:
  - method: MERGE
    merge-from: {name: General Goods Vendor}
    items: *FREE_ITEMS

    ```

[DONE]

[ACCORDION-END]

---
