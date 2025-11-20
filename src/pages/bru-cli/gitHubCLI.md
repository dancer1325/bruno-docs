# GitHub Actions Integration

* [GitHub Actions](https://docs.github.com/en/actions)
  * == CI/CD platform /
    * enables you to
      * | your GitHub repository, AUTOMATE your software development workflows
      * AUTOMATE API testing workflows
        * Reason:🧠integration -- with -- GitHub's ecosystem🧠 

* Bruno CLI
  * integrates -- with -- GitHub Actions
    * Reason:🧠automate API testing workflows🧠
    * _Example:_ https://github.com/bruno-collections/github-actions


## Prerequisites
- [Git](https://git-scm.com/downloads)
- GitHub repository / has Bruno collection


## Automate API Testing with GitHub Actions

1. | your repository,
   * 👀your Bruno collections MUST be properly organized👀 

    ```
    your-api-project/
    ├── .github/
    │   └── workflows/
    │       └── api-tests.yml
    ├── collections/
    │   ├── authentication/
    │   │   ├── login.bru
    │   │   └── logout.bru
    ├── environments/
    │   ├── development.bru
    │   ├── ci.bru
    │   └── production.bru
    └── bruno.json
    ```
   * ".github/workflows/api-tests.yml"

* TODO:
```yaml
name: API Tests

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4
      
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20'
    
    - name: Install Bruno CLI
      run: npm install -g @usebruno/cli
    
    - name: Run API Tests
      run: bru run --env ci --reporter-html results.html
    
    - name: Upload Test Results
      uses: actions/upload-artifact@v4
      with:
        name: test-results
        path: results.html
```

4. **Commit and push** your workflow file:
```bash
git add .github/workflows/api-tests.yml
git commit -m "Add GitHub Actions workflow for API testing"
git push origin main
```

5. **Monitor the workflow**:
   - Go to your GitHub repository
   - Click on the "Actions" tab
   - You should see your workflow running

6. **View results**:
   - Once completed, download the test results from the artifacts section
   - Open `results.html` in your browser for detailed reports

## Learn More

* [GitHub Actions documentation](https://docs.github.com/en/actions)
