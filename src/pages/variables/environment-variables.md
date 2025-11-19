# Environment Variables

* Environment variables
  * == variables /
    * 's scope
      * == environment
        * _Examples:_ local, development, production
  * uses
    * variables / 
      * can be re-used ACROSS the collection
      * are DIFFERENT -- depending on the -- environment
  * _Examples:_ server host url

## Creating an Environment Variable

* steps
  * | Bruno,
    * environments (top right) > **No environment**
      * if there are NO environments -> prompted to create one > Create

        ![No-Environment](/public/screenshots/variables/collection-environment.webp)
        * add name & value

          ![Environment Variables location](/public/screenshots/variables/environment-variables.webp)

## Using an Environment Variable

* steps
  * | Bruno, 
    * environment (top-right), choose 1
    * | request,
      * `{{varName}}`
        * == syntax

## Using the "./environments" directory

* "/environments" directory 
  * 💡| your collection💡
  * \>= 1 environments
    * == "<environment-name>.bru" file

      ```filename="local.bru"
      vars {
        host: http://localhost:8787
      }
      ```
