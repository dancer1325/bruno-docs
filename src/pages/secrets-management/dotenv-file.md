# Secrets Management

## DotEnv File (".env")

* Environment variables
  * way to manage them
    * 👀-- through -- ".env" files👀
  * uses
    * store 
      * sensitive data
        * _Examples:_ API keys, tokens
      * configuration settings -- outside the -- source code
  * allows
    * keep your code secure
    * makes it easier -- to -- manage DIFFERENT settings / various environments

## DotEnv File (.env) -- for -- Secret Management

* create ⚠️MANUALLY⚠️ 
  * | 💡**root** of your collection folder💡
    * _Example of your folder collection structure:_ 

      ```
      <FileTree.Folder name="bruno-collection" defaultOpen>
        <FileTree.Folder name="api-folder">
          <FileTree.Folder name="customer-api" />
          <FileTree.Folder name="emp-api">
            <FileTree.File name="details.bru" />
          </FileTree.Folder>
          <FileTree.File name="lib.js" />
        </FileTree.Folder>
        <FileTree.File name=".env" />
        <FileTree.File name=".gitignore" />
        <FileTree.File name="bruno.json" />
        <FileTree.File name="package.json" />
      </FileTree.Folder>
      ```
  * _Example of ".env":_

    ```filename=".env" showLineNumbers
    JWT_TOKEN=your_jwt_token_value
    API_KEY=your_api_key_value
    ```
  * ⚠️if the environment variables name contain dots -> use square bracket notation⚠️
    * _Example:_

      ```filename=.env
      example.test=mysecretvalue
      ```

        ```javascript, fileName=local.bru
        // NOT work
        "secret": "{{process.env.demo.example.test}}"
        
        // Works
        "secret": "{{process.env['example.test']}}"
        ```

* way to access | your Bruno collection
  * `process.env.secretName`
    * _Example of environment file ("environments/local.bru"):_

      ```filename="local.bru"
      vars {
        baseURL: https://echo.usebruno.com
        JWT_TOKEN: {{process.env.JWT_TOKEN}}
        API_KEY: {{process.env.API_KEY}}
      }
      ```

      ![dot env vars](/public/screenshots/dot-env-vars.webp)

## Managing Secrets

* | ".gitignore",
  * ⚠️add `.env` file⚠️
    * if you want to share your environment variables structure -> create a ".env.sample" file WITHOUT actual secret values
