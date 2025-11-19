# Variables

### Overview

* Variables
  * allow you to
    * store dynamic values
    * reuse them ACROSS MULTIPLE API requests & environments & workflows
  * ->
    * flexibility
    * maintainability
    * efficiency
  * _Examples:_ 
    * tokens,
    * environment-specific URLs
    * user-defined values

### Types

* types / 
  * can be created
    - [Global Environments Variables](./global-environment-variables.md)
    - [Environment Variables](./environment-variables.md)
    - [Collection Variables](./collection-variables.md)
    - [Folder Variables](./folder-variables.md)
    - [Request Variables](./request-variables.md)
    - [Runtime Variables](./runtime-variables.md)
      - ⚠️the highest precedence⚠️

* [Process Environment Variables](./process-env.md)
  * can be defined | 
    * ⚠️external environment configuration file⚠️
  * are accessed -- via -- `{{process.env.VAR_NAME}}` syntax
    * ❌NOT related to the PREVIOUS ones❌

### Variable Precedence and Scope

* variable's priority
  * == value / use

![](/public/screenshots/variables/variablePrecedence.png)

### Variable Storage

* 👀type of storage👀
  * file
    * == persistent
  * app's memory
    * 👀== tempora👀
      * == | close Bruno, they are lost

| Variable Type       | Storage Location      |
|---------------------|-----------------------|
| Collection          | <collection-name>.bru |
| Folder              | <folder-name>.bru     |
| Request             | <request-name>.bru    |
| Environment         | <env-name>.bru        |
| Runtime             | app's memory          |
| Global              | app's memory          |
| Process Environment | .env file             |

### Variable Data Type

* 👀string👀

### Debugging Variables | Console

* `bru.get[Type]Var(key)`
  - variables' syntax
  - `[Type]`
    - == [variable type](#types)
  - `key`
    - == variable name / you want to access

* _Example:_ 

    ```javascript
    // Basic syntax: console.log(bru.get[Type]Var(key))
    console.log(bru.getVar('myVar'))           // Runtime variables
    ```

### Scripting API

* [Scripting API](/src/pages/testing/script/javascript-reference.md#variables)
  * how to access variables | your scripts
