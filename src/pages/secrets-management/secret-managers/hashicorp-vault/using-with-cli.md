# Using with Bruno CLI
## Pre-requisites

* | collection's **secrets.json** file,
  * add the vault connection configuration 
    * ALLOWED to use environment variables

## Usage

#### Vault server / token authentication

```json filename="secrets.json"
{
  "type": "vault",
  "cli": {
    "type": "vault-server",
    "vaultServerConfig": {
      "url": "http://localhost:8200",
      "namespace": "bruno",
      "auth": {
        "method": "token",
        "token": "{{authToken}}"
      }
    }
  },
  "data": [
    {
      "environment": "Prod",
      "secrets": [
        {
          "name": "db",
          "path": "secret/db",
          "enabled": true
        }
      ]
    }
  ]
}
```

* `bru run folder --env Prod --env-var authToken=your-vault-token`
  * CLI command

#### Vault server / appRole authentication

```json filename="secrets.json"
{
  "type": "vault",
  "cli": {
    "type": "vault-server",
    "vaultServerConfig": {
      "url": "http://localhost:8200",
      "namespace": "bruno",
      "auth": {
        "method": "app_role",
        "appRole": {
          "role": "bruno",
          "roleId": "{{roleId}}",
          "secretId": "{{secretId}}"
        }
      }
    }
  },
  "data": [
    {
      "environment": "Prod",
      "secrets": [
        {
          "name": "db",
          "path": "secret/db",
          "enabled": true
        }
      ]
    }
  ]
}
```

* `bru run folder --env Prod --env-var roleId=your-role-id --env-var secretId=your-secret-id`
  * CLI command

#### Vault cloud / client credentials authentication

```json filename="secrets.json"
{
  "type": "vault",
  "cli": {
    "type": "vault-cloud",
    "vaultCloudConfig": {
      "auth": {
        "method": "client-credentials",
        "clientCredentials": {
          "tokenEndpoint": "{{tokenEndpoint}}",
          "secretsEndPoint": "{{secretsEndpoint}}",
          "clientId": "{{clientId}}",
          "clientSecret": "{{clientSecret}}"
        }
      },
      "project": {
        "name": "{{projectName}}",
        "projectId": "{{projectId}}",
        "organizationId": "{{organizationId}}"
      }
    }
  },
  "data": [
    {
      "environment": "Prod",
      "secrets": [
        {
          "name": "db",
          "path": "secret/db",
          "enabled": true
        }
      ]
    }
  ]
}
```

* `bru run folder --env Prod --env-var tokenEndpoint=your-token-endpoint --env-var secretsEndpoint=your-secrets-endpoint --env-var clientId=your-client-id --env-var clientSecret=your-client-secret --env-var projectName=your-project-name --env-var projectId=your-project-id --env-var organizationId=your-organization-id`
  * CLI command
