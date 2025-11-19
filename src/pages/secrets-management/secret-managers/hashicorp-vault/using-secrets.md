# Using secrets<PremiumBadge />

![vault-selected](/public/screenshots/secret-variables/hashicorp-vault/using-secrets/1-using-secrets.webp)

## | Request Fields

* `$secrets.<secret-name>.<key-name>`
  * way to access them
    * == way to access collection & environment variables

* uses | request fields
  * headers,
  * query,
  * body,
  * auth input

## | Scripts

* `bru.getSecretVar()` 
  * == function / 
    * enables you to,
      * access secrets | Pre-request & Post-request scripts 
  * _Example:_

    ```javascript
    const secretValue = bru.getSecretVar('<secret-name>.<key-name>');
    console.log(secretValue); // This will log the value of your secret
    
    // Example
    const apiKey = bru.getSecretVar('payment-service.api-key');
    req.setHeaders('x-api-key: ' + apiKey);
    ```
