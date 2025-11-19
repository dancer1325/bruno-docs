# Configuring and Fetching secrets

* steps
  * | Bruno
    * Collections > **Collection Settings** > **Secrets**

        ![select-provider](/public/screenshots/secret-variables/hashicorp-vault/config-and-fetching-secrets/1-select-provider.webp)
      * Select Provider == Vault

        ![vault-selected](/public/screenshots/secret-variables/hashicorp-vault/config-and-fetching-secrets/2-vault-selected.webp)

      * ⚠️choose an environment⚠️
        * Reason:🧠secrets are environment-specific🧠
      * if you want to 
        * add a NEW secret -> 
          * click `+ Add Secret` button
            * Name == specifyOne
            * path == relativePathToStoreInVault

              ![add-secret](/public/screenshots/secret-variables/hashicorp-vault/config-and-fetching-secrets/3-add-secret.webp)
        * fetch secrets -> 
          * click `Fetch Secrets`
            * choose 1 secret providers
            * click `Fetch` button

              ![fetch-secrets](/public/screenshots/secret-variables/hashicorp-vault/config-and-fetching-secrets/4-fetch-secrets.webp)

          * fetched secrets will be displayed | table

              ![fetched-secrets](/public/screenshots/secret-variables/hashicorp-vault/config-and-fetching-secrets/5-get-valut-values.webp)
