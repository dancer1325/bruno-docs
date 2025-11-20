# Whitelisting Modules

* TODO:
The scripts can use both [external libraries](external-libraries) (via package.json and npm install) and certain [built-in](inbuilt-libraries) modules in Node.js (like fs, path, etc.)
* However, for security reasons, not all built-in Node.js modules are made accessible by default in Bruno scripts.

## Why Whitelisting

Bruno requires you to explicitly enable (whitelist) modules before they can be used in scripts due to security reasons. The whitelisting process ensures that only the modules you specifically choose to enable will be available to your scripts.

You can manually enable or whitelist these modules by editing your `bruno.json` file. Make sure to add the `script` section to the file.

```json copy filename="bruno.json" showLineNumbers {6-11}
{
  "version": "1",
  "name": "collection_name",
  "type": "collection",
  "ignore": ["node_modules", ".git"],
  "scripts": {
    "moduleWhitelist": ["child_process"],
    "filesystemAccess": {
      "allow": true
    }
  }
}
```

<Callout type="warning">
  filesystemAccess is required for reading and writing files, especially for
  modules that depend on it.
</Callout>


### Whitelisting Multiple Modules

If you need to use multiple built-in or trusted third-party modules in your Bruno script, you can whitelist them by adding them to the `moduleWhitelist` array. For example:

```json copy filename="bruno.json" showLineNumbers
 "scripts": {
      "moduleWhitelist": ["crypto", "jwt", "child_process"],
      "filesystemAccess": {
        "allow": true
      }
    }
```

Only whitelist modules that you trust and that are necessary for your script to function properly.




* steps
  * | bruno.json
    * 👀`scripts.moduleWhitelist`👀
      * ⚠️SOME built-in modules could require to set ALSO `scripts.filesystemAccess`⚠️
* use case
  * ❌NOT ALL built-in modules are accessible | scripts out of the box in Bruno❌
    * Reason: 🧠security reasons🧠
  * You can manually enable/whitelist these modules by modifying your `bruno.json`.


**Example:** TODO: create a dedicated example folder

To enable the `child_process` module, you can put the following in your `bruno.json` file:

```json
{
  "scripts": {
    "moduleWhitelist": ["child_process"],
    "filesystemAccess": {
      "allow": true
    }
  }
}
```

Note that `filesystemAccess` is required for `child_process` to work as expected
This may be required for other built-in modules as well
