# dotnet-build-test-publish-action
A GitHub Action to build, test, publish .NET projects, and run SonarCloud checks.

## Why Use This Action?

This action streamlines the CI/CD process for .NET projects by combining essential tasks into a single, reusable workflow. With this action, you can:
- **Automate Your Build Process**: Ensure that your .NET projects are consistently built in a reliable environment.
- **Run Tests Automatically**: Catch bugs early by running your tests automatically with each commit or pull request.
- **Integrate with SonarCloud**: Perform static code analysis with SonarCloud to maintain high code quality and detect potential issues.
- **Publish Artifacts**: Deploy your application or library by publishing it to a specified path.
- **Save Time and Reduce Errors**: Minimize manual steps and reduce the potential for human error by automating your CI/CD pipeline.

## Author

Artur Khutak

## Inputs

- `sonar-project-key`: SonarCloud project key. Default is '' if you want to skip SonarCloud checks and coverage collection.
- `sonar-token`: SonarCloud token. Default is '' if you want to skip SonarCloud checks and coverage collection.
- `sonar-organization`: SonarCloud organization. Default is '' if you want to skip SonarCloud checks and coverage collection.
- `sonar-host-url`: SonarCloud host url.
- `dotnet-solution-path`: Path to the dotnet solution file (.sln). Default is '' (root).
- `dotnet-version`: Dotnet version for actions/setup-dotnet. Default is '8.x'.

## Example usage

Create a `.github/workflows/your-workflow.yml` file in your repository:

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
      uses: ArtyProf/dotnet-build-test-publish-action@v1.1.0
      with:
        sonar-project-key: ${{ secrets.SONAR_PROJECT_KEY }} # Optional, default is ''
        sonar-token: ${{ secrets.SONAR_TOKEN }} # Optional, default is ''
        sonar-organization: ${{ secrets.SONAR_ORGANIZATION }} # Optional, default is ''
        sonar-host-url: ${{ secrets.SONAR_HOST }} # Optional, default is 'https://sonarcloud.io'
        dotnet-solution-path: './path/to/your/solution.sln' # Optional, default is '' (root)
        dotnet-version: '7.x' # Optional, default is '8.x'
```

### Summary

This `README.md` file now reflects your GitHub username and the filename for your action. Replace the placeholders in the example usage section with your actual project details.
