# Generating Reports

* Bruno CLI
  * generate reports 
    * | 
      * **JSON**,
        * uses
          * analyze test results
      * **JUnit**,
        * uses
          * integrate -- with -- CI/CD pipelines / rely on JUnit reporting
      * **HTML**
        * uses
          * quick reviews
    * uses
      * analyze test results
      * integrate -- with -- various CI/CD tools

### JSON Report

* `--reporter-json outputFile.json` option

* _Example:_ TODO:
```bash copy
bru run --reporter-json results.json
```

### JUnit Report

* `--reporter-junit outputFile.*` option
  * recommended `outputFile.xml`

* _Example:_ TODO:
```bash copy
bru run --reporter-junit results.xml
```

### HTML Report

* `--reporter-html outputFile.html` option

* _Example:_ TODO:
```bash copy
bru run --reporter-html results.html
```

### Running SIMULTANEOUSLY MULTIPLE Reporters

* _Example:_ TODO:
* For example, to generate JSON, JUnit, and HTML reports simultaneously, run:

```bash copy
bru run --reporter-json results.json --reporter-junit results.xml --reporter-html results.html
```

## Skipping Specific Headers | Report

* `--reporter-skip-headers "Header1" "Header2" "..."` option

* _Example:_ TODO:
```bash
bru run --reporter-html results.html --reporter-skip-headers "Authorization" "X-Auth-Token"
```

## Skip ALL Headers | output report

* `--reporter-skip-all-headers` option

* _Example:_ TODO:
```bash copy
bru run --reporter-html results.html --reporter-skip-all-headers
```
