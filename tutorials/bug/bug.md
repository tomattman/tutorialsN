---
title: BUG
description: The following steps will explain how to create a basic Java project to call OData services using the SAP S/4HANA Cloud SDK on Cloud Foundry.
tags: [ tutorial>intermediate, products>sap-s-4hana-cloud-sdk]
primary_tag: products>sap-s-4hana-cloud-sdk
time: 355
---

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
