# dotnet-build-test-publish-action
A GitHub Action to build, test, publish .NET projects, and run SonarCloud checks.

## Inputs

- `sonar-project-key` (required): SonarCloud project key.
- `sonar-token` (required): SonarCloud token.
- `sonar-organization` (required): SonarCloud organization.
- `sonar-host-url`: SonarCloud host url.
- `dotnet-solution-path`: Path to the dotnet solution file (.sln). Default is '' (root).
- `dotnet-version`: Dotnet version for actions/setup-dotnet. Default is '8.x'.
- `path-to-publish`: Path for dotnet publish. Default is './publish'.

## Example usage

```yaml
name: Build, Test, and SonarCloud

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Use .NET Build, Test, SonarCloud check and Publish Action
      uses: ArtyProf/dotnet-build-test-publish-action@v1
      with:
        sonar-project-key: ${{ secrets.SONAR_PROJECT_KEY }}
        sonar-token: ${{ secrets.SONAR_TOKEN }}
        sonar-organization: ${{ secrets.SONAR_ORGANIZATION }}
        sonar-host-url: ${{ secrets.SONAR_HOST }} # Optional, default is 'https://sonarcloud.io'
        dotnet-solution-path: './path/to/your/solution.sln' # Optional, default is '' (root)
        dotnet-version: '7.x' # Optional, default is '8.x'
        path-to-publish: './custom-publish-path' # Optional, default is './publish'
```

### Summary

This `README.md` file now reflects your GitHub username and the filename for your action. Replace the placeholders in the example usage section with your actual project details. This will help users understand how to use your custom action in their workflows.
