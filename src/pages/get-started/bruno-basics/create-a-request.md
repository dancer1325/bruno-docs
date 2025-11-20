# Creating a Request

* support
  * various API protocols
    * HTTP
    * GraphQL
    * cURL 
  * ALL standard HTTP methods (GET, POST, PUT, DELETE, etc.)
 
## How to create a NEW Request | Bruno UI?

* steps
  * | Bruno UI,
    * Collection > `···` button > `New Request`

      ![create request dialog](../../../../public/screenshots/get-started/bruno-basics/create_request/1-create-new-request.webp)
      * Request Type: choose 1 -- of -- HTTP, GraphQL, from cURL
      * Request Name: choose 1
      * HTTP Method: choose 1 -- GET, POST, PUT, etc. --
      * URL

      ![create-new-request](../../../../public/screenshots/get-started/bruno-basics/create_request/2-create-request.webp)

## Custom Request Filenames 

* requirements
  * [Bruno v1.40.0](https://www.usebruno.com/downloads)

* ALLOWED customizations | request filenames
  * the filename itself
  * use special characters
    * _ExampleS:_ `/`, `[`, `]`, `*`, etc
    * if you use NOT valid ones -> Bruno AUTOMATICALLY handles them -- by replacing with -- `-`

* steps
  * | Bruno UI,
    * **Show Filesystem Name.**

      ![file-system-name](../../../../public/screenshots/get-started/bruno-basics/create_request/3-file-system-option.webp)
      * display the request name / stored | filesystem

        ![file-system-name](../../../../public/screenshots/get-started/bruno-basics/create_request/4-file-name-special-char.webp)
