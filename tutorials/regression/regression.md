---
title: MY_2205
description: example
tags: [products>sap-hana, topic>api, tutorial>beginner]
primary_tag: tutorial:product/mobile
---



[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]
    
First Header | Second Header | Third Header | Fourth Header | Fifth Header | Sixth Header
------------ | ------------- | ------------ | ------------- | -------------| -------------
Content from cell 1 | Content from cell 2 | Content from cell 3 | Content from cell 4 | Content from cell 5 | Content from cell 6
Content.js in the first column | Content in the second column | Content in the third column | Content in the fourth column | Content in the fifth column.js | Content in the sixth column

[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]

```html
	 <!DOCTYPE HTML>
	 <html>
	 <head>
		 <meta http-equiv="X-UA-Compatible" content="IE=edge" />
		 <meta charset="UTF-8"/>
		 <title>My Sensor Data</title>
		 <script id='sap-ui-bootstrap'
		 	src='/sap/ui5/1/resources/sap-ui-core.js'
		 	data-sap-ui-theme='sap_goldreflection'
		 	data-sap-ui-libs='sap.ui.core,sap.ui.commons,sap.ui.table'></script>
		 <script language="JavaScript">
			 var oModel = new sap.ui.model.odata.ODataModel("/<userid>trial/codejam/iotmmsxs/iotservice.xsodata/", false);
			 var arrayHeaders = new Array();
			 	oTable = new sap.ui.table.Table("test",{tableId: "tableID", visibleRowCount: 10});
			 //Bring the table onto the UI
			 oTable.placeAt("sensor_table");
			 //Table Column Definitions
			 var oMeta = oModel.getServiceMetadata();
			 var oControl;
			 for ( var i = 0; i < oMeta.dataServices.schema[0].entityType[0].property.length; i++) {
			 var property = oMeta.dataServices.schema[0].entityType[0].property[i];
			  oControl = new sap.ui.commons.TextField().bindProperty("value",property.name);
			  oTable.addColumn(new sap.ui.table.Column({label:new sap.ui.commons.Label({text: property.name}), template: oControl, sortProperty: property.name, filterProperty: property.name, filterOperator: sap.ui.model.FilterOperator.EQ, flexible: true, width: "125px" }));
			    }
			 oTable.setModel(oModel);
			 var sort1 = new sap.ui.model.Sorter("C_TIMESTAMP");
			 <body>
			oTable.bindRows("/<table name>",sort1);
		 </script>
	 </head>
	  <div id="sensor_table"/>
	 </body>
	 </html>
	```
[DONE]
[ACCORDION-END]
    
[ACCORDION-BEGIN [STEP 12](Accordion component which contains code block and no code block in Body)]

```json
{
     "firstName": "John",
     "lastName" : "Smith",
     "age"      : 25,
     "address"  :
     {
         "streetAddress": "21 2nd Street",
         "city"         : "New York",
         "state"        : "NY",
         "postalCode"   : "10021"
     },
     "phoneNumber":
     [
         {
           "type"  : "home",
           "number": "212 555-1234"
         },
         {
           "type"  : "fax",
           "number": "646 555-4567"
         }
     ]
 }
 {
        "name":"Product",
        "properties":
        {
                "id":
                {
                        "type":"number",
                        "description":"Product identifier",
                        "required":true
                },
                "name":
                {
                        "type":"string",
                        "description":"Name of the product",
                        "required":true
                },
                "price":
                {
                        "type":"number",
                        "minimum":0,
                        "required":true
                },
                "tags":
                {
                        "type":"array",
                        "items":
                        {
                                "type":"string"
                        }
                },
                "stock":
                {
                        "type":"object",
                        "properties":
                        {
                                "warehouse":
                                {
                                        "type":"number"
                                },
                                "retail":
                                {
                                        "type":"number"
                                }
                        }
                }
        }
}
{
        "id": 1,
        "name": "Foo",
        "price": 123,
        "tags": ["Bar","Eek"],
        "stock": { "warehouse":300, "retail":20 }
}
```
[ACCORDION-END]

