# How to Add a Secret Provider?

* 👀supported Hashicorp Vault / can be integrate👀
  * [HashiCorp Cloud Vault](https://developer.hashicorp.com/hcp)
  * [Vault Enterprise Server](https://developer.hashicorp.com/vault/docs/enterprise)
  * [Local Vault server](https://developer.hashicorp.com/vault/docs/install)

## Setting Up Vault Server

* 👀supported authentications👀
  * **Token**
  * **AppRole**

* steps
  1. | Bruno,
     * application > settings > **Secrets Manager** > **Add Secret Provider**

       ![vault-secrets](/public/screenshots/secret-variables/hashicorp-vault/adding-a-secret-provider/1-secrets-home-window.webp)

     * Type == **Vault Server**

       ![vault-secrets-window](/public/screenshots/secret-variables/hashicorp-vault/adding-a-secret-provider/2-local-vault-secrets.webp)

     * URL 
       * if you use a 
         * Vault local server -> == http://localhost:8200
         * Vault hosted server -> == https://vault.example.com
     * * Auth method & Token == choose one
       * [Token](https://developer.hashicorp.com/vault/docs/commands/token) OR
       * [AppRole <strong><sup>↗</sup></strong>](https://developer.hashicorp.com/vault/tutorials/auth-methods/approle)
     * **Add**

       ![vault-added-screen](/public/screenshots/secret-variables/hashicorp-vault/adding-a-secret-provider/3-added-vault.webp)

## Setting up Vault Cloud

* steps
  1. | Bruno,
     * application > settings > **Secrets Manager** > **Add Secret Provider**
     * Type == **Vault Cloud**

       ![vault-secrets](/public/screenshots/secret-variables/hashicorp-vault/adding-a-secret-provider/4-vault-cloud-setup.webp)
     * `Token Endpoint` & `Secrets Endpoint`
       * if you have CUSTOM ones -> modify them
         * ⚠️OTHERWISE, leave the default ones⚠️
     * [Client Credentials](https://developer.hashicorp.com/hcp/docs/hcp/admin/iam/service-principals)
     * Projects > **Add**
