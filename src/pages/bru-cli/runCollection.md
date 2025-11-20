# Running a Collection 

* 👀ways / Bruno CLI runs your API collections👀
  * executing requests OR
  * using external data sources

* goal
  * how to 
    * run entire collections, specific folders
    * use data sources (CSV and JSON files) -- to -- drive your API tests

## Running ALL Collection

* | your collection directory,
  * `bru run`

## Running a Collection's Folder 

* | your collection directory,
  * `bru run <folder-name>`

* _Examples:_ TODO:

## Running a Collection -- via -- CSV File

* requirements
  * Bruno CLI v1.35.0+

* `bru run --csv-file-path /path/to/csv/file.csv`
  * execute the collection 1! / EACH CSV file's row
    * EACH row's data == variables | your requests

* _Examples:_ TODO:

## Running a Collection with a JSON File

To run a collection using data from a JSON file, provide the file path using the `--json-file-path` option:

```bash copy
bru run --json-file-path /path/to/json/file.json
```
## Running a Collection Multiple Times

You can run a collection multiple times in a single command using the `--iteration-count` flag:

```bash copy
bru run --iteration-count=2
```

This will execute the collection twice. This is useful for load testing or when you need to repeat the same set of requests multiple times.

## Running a Collection -- with -- Environments

* ALLOWED format types / store the environment variables
  * [".bru" file](#using-environment-files)
  * [".json" file](#using-json-environment-files)

* `--env-file /path/to/environment.*` option
  * ALLOWED /path/to/environment
    * relative
    * absolute

### Using Environment Files

* `bru run --env-file /path/to/environment.bru`

```bash copy
# Using relative path
bru run --env-file ./environments/local.bru

# Using absolute path
bru run --env-file /Users/username/projects/api-testing/environments/prod.bru
```

### Using JSON Environment Files

* requirements
  * [Bruno CLI v2.13.0+](https://www.npmjs.com/package/@usebruno/cli)

* use cases
  * global environments / created | Bruno app
    * == 👀bridges the gap BETWEEN UI-ONLY global environments -- & -- CLI-based workflows👀

* `bru run --env-file /path/to/environment.json`

#### JSON Environment File Format

The JSON environment file should follow Bruno's environment schema:

```json copy
{
  "name": "My Environment",
  "variables": [
    { 
      "name": "host", 
      "value": "https://api.example.com", 
      "enabled": true 
    },
    { 
      "name": "api_key", 
      "value": "your-api-key-here", 
      "enabled": true 
    }
  ]
}
```

### Using Environments Names

If you need to use a specific environment, you can pass it with the `--env` option:

```bash copy
bru run --env Local
```

#### Passing Environment Variables

<Callout type="info">
Variables marked as secrets in Bruno app are not accessible via the CLI. Pass them directly as command-line arguments.
</Callout>

```bash copy
bru run --env Local --env-var JWT_TOKEN=1234
```

## Multiple Environment Variables

You can override multiple environment variables by using additional `--env-var` flags:

```bash copy
bru run --env Local --env-var JWT_TOKEN=1234 --env-var API_KEY=abcd1234 
```

Each `--env-var` flag adds or overrides a single environment variable, and you can chain as many as needed.

## Filtering Requests with Tags

Bruno CLI supports filtering requests by tags, allowing you to run only specific subsets of your collection based on tag criteria.

<Callout type="info">
  This feature requires [Bruno CLI <strong><sup>↗</sup></strong>](https://www.npmjs.com/package/@usebruno/cli) version 2.8.0 or higher.
</Callout>

### Include Tags

Run only requests that have at least one matching tag.

```bash copy
bru run --tags=smoke,sanity
```

### Exclude Tags

Skip requests that have ANY of the specified tags:

```bash copy
bru run --exclude-tags=skip,draft
```

### Combined Filtering

You can combine include and exclude filters:

```bash copy
bru run --tags=smoke,sanity --exclude-tags=skip,draft
```

## Parallel Execution and Progress Tracking

Bruno CLI supports running requests in parallel and displaying real-time progress during collection execution.

### Parallel Execution

By default, Bruno CLI runs requests sequentially. You can enable parallel execution using the `--parallel` flag:

```bash copy
bru run --iteration-count 2 --parallel
```


