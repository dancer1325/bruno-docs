# Script Flow in Bruno

* script flows
  * allows
    * control the execution order of your API test collections
  * types
    * [**Sandwich**](#sandwich-flow)
    * [**Sequential (Natural)**](#sequential-natural-flow)

## Sandwich Flow

* scripts execution order

    ```bash
    sandwich-flow/
    ├── Collection Pre Script
    │   └── Folder Pre Script
    │       └── Request Pre Script
    └── Request Post Script
        └── Folder Post Script
            └── Collection Post Script
    ```

* allows you to
  * BEFORE & AFTER EACH test,
    * execute actions | MULTIPLE levels (collection, folder, and request) 
* uses
  * configure different environments or states before and after running tests at various levels.

## Sequential (Natural) Flow

* scripts execution order

  ```bash
  sequential-flow/
  ├── Collection Pre Script
  │   └── Folder Pre Script
  │       └── Request Pre Script
  └── Collection Post Script
      └── Folder Post Script
          └── Request Post Script
  ```

This flow executes scripts in a more natural, linear order
After the **Request Pre Script**, it runs the **Collection Post Script**, followed by **Folder Post Script**, and finally, the **Request Post Script**
This flow may be better suited when you want a clean execution from top to bottom.

<Callout emoji="">
  If the `flow` property is not specified, Sandwich is used by default.
</Callout>

You can set the flow type (either `sandwich` or `sequential`) in your `bruno.json` configuration file:

```json showLineNumbers filename="bruno.json" {7}
{
  "scripts": {
    "moduleWhitelist": ["crypto", "buffer", "form-data"],
    "filesystemAccess": {
      "allow": true
    },
    "flow": "sequential" // Or "sandwich"
  }
}
```
