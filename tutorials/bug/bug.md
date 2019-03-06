---
title: BUG
description: The following steps will explain how to create a basic Java project to call OData services using the SAP S/4HANA Cloud SDK on Cloud Foundry.
auto_validation: true
tags: [ tutorial>intermediate, products>sap-s-4hana-cloud-sdk, products>sap-cloud-platform, products>sap-cloud-platform-connectivity, products>sap-s-4hana, topic>cloud, topic>java, topic>odata ]
primary_tag: products>sap-s-4hana-cloud-sdk
---

## Prerequisites  
 - **Proficiency:** intermediate
 - In order to follow this tutorial successfully, you need a working and reachable system of `SAP S/4HANA on-premise` or `S/4HANA Cloud`. You may substitute the cost center service introduced here with any other API published on the SAP API `BusinessHub`. If you do not have an `S/4HANA` system available, you may use a public service such as the [Northwind OData Service](http://services.odata.org/V2/Northwind/Northwind.svc) as a fallback solution.


[ACCORDION-BEGIN [Step 5: ](Deploying the Project)]

```markdown
---

applications:

- name: firstapp
  memory: 768M
  host: firstapp-D123456
  path: application/target/firstapp-application.war
  buildpack: sap_java_buildpack
  env:
    TARGET_RUNTIME: tomee
    JBP_CONFIG_SAPJVM_MEMORY_SIZES: 'metaspace:96m..'
    SET_LOGGING_LEVEL: '{ROOT: INFO, com.sap.cloud.sdk: INFO}'
    ALLOW_MOCKED_AUTH_HEADER: true
  services:
  - my-destination
  - my-xsuaa
#  - my-application-logs
#  - my-connectivity
```

[DONE]

[ACCORDION-END]

---
