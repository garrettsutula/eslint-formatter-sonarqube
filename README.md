# eslint-formatter-sonarqube

This formatter aggregates the ESLint results into JSON format that can be imported into your sonarqube 7.4+ projects. After installing this module, configure your `sonar-project.properties` file to add the parameter `sonar.externalIssuesReportPaths` with one or more paths to reports that will be imported when a scan is run.

## Installation & Usage

*To Install*
```
npm install eslint-formatter-sonarqube --save-dev
```

*Once installed*, pass the module as the formatter parameter when using eslint:
```
eslint -f node_modules/eslint-formatter-sonarqube -o ./sonar/result.json  ./  
```

## Reference

- [ESLint documentation](https://eslint.org/docs/developer-guide/working-with-custom-formatters)  on custom formatters
- [SonarQube documentation](https://docs.sonarqube.org/display/SONAR/Generic+Issue+Data) on external analyzers 
