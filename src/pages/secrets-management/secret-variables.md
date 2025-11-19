# Secrets Management

## Secret Variables

* Bruno
  * stores secrets | 👀your local machine👀 /
    * 's location -- depends on the -- OS
    * encrypted -- via --
      * OS level encryption, OR
      * by default, AES256 encryption
    * managed internally
      * == ❌NOT write them | environment file❌
    * | export your collection as a file, 
      * ❌Bruno does NOT export the secret variables❌
    * | environment file,
      * appears ONLY definition
      * ❌NOT store the value❌
      
![secret variables](/public/screenshots/secret-variables.webp)

```bru filename="environments/local.bru"
vars {
  url: https://echo.usebruno.com
}
vars:secret [
  jwt-token
]
```
