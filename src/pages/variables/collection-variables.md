# Collection Variables

* Collection variables
  * == variables / 
    * 's scope == specific collection
  * uses
    * store variables / used ACROSS MULTIPLE requests | collection

## How to create?

* steps
  * | Bruno UI,
    * Collection > Settings > Variables tab
      * Pre Request
        * Name: specify
        * Value: specify
      * Post Response
        * Name: specify
        * Value: specify

    ![Collection Variables](../../../public/screenshots/variables/collection-variables.webp)

## How to use?
### | request
* `{{varName}}`

![Collection Variables Usage](../../../public/screenshots/variables/collection-variables-usage.webp)

### | scripts
* `bru.getCollectionVar("varName")`

* _Example:_ TODO:
```javascript
let namespace = bru.getCollectionVar("namespace");
```

## Import/Export Collection Variables

* ReasonS:🧠
  * share them ACROSS teams
  * back them up🧠

### Accessing Import/Export Options

* TODO:
1. Go to the **Environments** section (top right corner).

![No-Environment](../../../public/screenshots/variables/no-environment.webp)

2. Click on **Configure** to access the environment settings.

3. You will see the **Import** and **Export** options in the bottom left corner.

![Export Option](../../../public/screenshots/variables/click-export-option.webp)

### Importing Environment Variables

The import feature accepts environment files in both **Bruno** and **Postman** formats:

1. Click on the **Import** button.
2. Select the environment file you want to import
3. The variables will be added to your collection.

### Exporting Environment Variables

1. Click on the **Export** button.
2. If you have multiple environments, select which environments you want to export.
3. Choose the location where you want to save the exported JSON file.

![Export Collection Environment Location](../../../public/screenshots/variables/export-collection-env-location.webp)

4. The environment variables will be saved as a JSON file that can be shared or backed up.

<Callout type="warning">
  Secret variables (variables marked as secret) will not be included in the exported JSON file for security reasons.
</Callout>
