# Process Environment Variables

## Overview

* Process environment variables
  * uses
    * store sensitive information (API keys, passwords, and other secret values)
  * stored | ".env" file
    * ⚠️you need to create MANUALLY⚠️
  * [secret management](../secrets-management/dotenv-file)

### Creating a Process Environment Variables

* steps
  * add a ".env" file | root of your Bruno collection

#### Example

* TODO: create a dedicated example
In your Bruno collection, the structure might look like this:

```
bruno-collection/
├── api-folder/
│   ├── customer-api/
│   ├── emp-api/
│   │   └── details.bru
│   └── lib.js
├── .env
├── .gitignore
├── bruno.json
└── package.json
```

In the `.env` file, you would store a key-value pair, like this:

```bash showLineNumbers filename=".env"
key = bruno
```

### How to use the Process Environment Variables?

* `process.env`
  * global object
  * `process.env.<secret-name>` 

    ![image](/bruno-docs/public/screenshots/variables/creating-process-env-variables.webp)

    ![image](/bruno-docs/public/screenshots/variables/using-process-env-variables.webp)
