# Bru Tag Reference

## meta

* == your request's metadata 
* `meta`
  * `seq`
    * uses
      * sequence number | ⚠️IMMEDIATE parent folder⚠️
        * == 👀sort position of your request | UI👀
  * `type`
    * ALLOWED values
      * `http`
      * `graphql`
  * `tags`
    * == array of strings 
      * _ExampleS:_ environment, functionality, or priority
    * allows
      * | run collections, 
        * filter requests
      * organize requests

## get

* == make a `GET` http call
* `get`

## post

* == make a `POST` http call
* `post`

## put

* == make a `PUT` http call
* `put`

## delete

* == make a `DELETE` http call
* `delete`

## options

* == make a get `OPTIONS` call
* `options`

## trace

* == make a `TRACE` http call
* `trace`

## connect

* == make a `CONNECT` http call
* `connect`

## head

* == make a `HEAD` http call
* `head`

## query

* == request query params
* `params:query`

## path

* == request path params
* `params:path`

## headers

* == request query headers
* `headers`

## body

* == request body
  * by default, json

## `body:text`

* == request body -- as -- text

## `body:xml`

* == request body -- as -- xml

## `body:form-urlencoded`

* == request body -- as -- form-urlencoded

## `body:multipart-form`

* == request body -- as -- multipart-form

## `body:graphql`

* == request body -- as -- graphql

## `body:graphql:vars`

* == request body -- as -- graphql vars

## `script:pre-request`
* == request body -- as -- pre-request

## `script:post-response`
* == request body -- as -- post-response

## `body:test`
* == tests
