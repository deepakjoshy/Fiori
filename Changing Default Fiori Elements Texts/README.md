## Changing default texts in Fiori Elements Templates



SAP Web IDE automatically generates the following folders and files when you create an app with SAP Fiori elements:

-  [Root Folder]

- |—i18n

- |— [shortened template component name], for example, List Report and Object Page

- |—[entitySet]

- |—i18n.properties


The folder path to the resource model appears as shown below. Since the manifest.json file also refers to the title and description of the app, there is a general i18n.properties file on the top level:

i18n.properties
i18n/ListReport/[entitySet]/POHeaders/i18n.properties
i18n/ObjectPage/[entitySet]/i18n.properties
i18n/ObjectPage/[subEntitySet]/i18n.properties

**Note** : For object pages, the number of i18n files corresponds to the number of object pages defined in the app.



The app descriptor (manifest.json file) of an application specifies the SAPUI5 models.

Example:
```javascript
"sap.ui5": { 
    "models": {
        "i18n": {                
            "type": "sap.ui.model.resource.ResourceModel",                
            "uri": "i18n/i18n.properties"           
      },
 
        "i18n|sap.suite.ui.generic.template.ListReport|POHeaders": {
            "type": "sap.ui.model.resource.ResourceModel",
            "uri": "i18n/ListReport/POHeaders/i18n.properties"
              },
        "i18n|sap.suite.ui.generic.template.ObjectPage|POHeaders": {
                    "type": "sap.ui.model.resource.ResourceModel",
                    "uri": "i18n/ObjectPage/POHeaders/i18n.properties"
              },
        "i18n|sap.suite.ui.generic.template.ObjectPage|POItems": {
                    "type": "sap.ui.model.resource.ResourceModel",
                    "uri": "i18n/ObjectPage/POItems/i18n.properties"
```

The URL reflects the folder path to the resource model. The model's name, i18n|sap.suite.ui.generic.template.ObjectPage|POHeaders, is separated by lines used to identify the specific template component and entity set for which the resource model can be enhanced by editing the i18n.properties file.
