# eslint-formatter-sonarqube

> **This project is archived and no longer maintained.**
>
> SonarQube now has native ESLint support that reads ESLint's built-in JSON format directly — no custom formatter is needed. See the instructions below for the recommended approach.

---

## Recommended approach (native ESLint + SonarQube integration)

### 1. Generate an ESLint JSON report

Use ESLint's built-in `json` formatter to write a report file:

```sh
eslint --format json --output-file ./sonar/eslint-report.json .
```

### 2. Configure SonarQube

In your `sonar-project.properties` file, point `sonar.eslint.reportPaths` at the report:

```properties
sonar.eslint.reportPaths=sonar/eslint-report.json
```

Multiple paths are comma-separated:

```properties
sonar.eslint.reportPaths=sonar/eslint-report.json,sonar/eslint-report-tests.json
```

SonarQube will import the ESLint findings as issues on the next scan.

---

## Legacy usage (archived)

This formatter converted ESLint output to SonarQube's Generic Issue Data format for use with `sonar.externalIssuesReportPaths`. It is no longer recommended.

## Reference

- [ESLint documentation](https://eslint.org/docs/developer-guide/working-with-custom-formatters) on custom formatters
- [SonarQube documentation](https://docs.sonarqube.org/latest/analyzing-source-code/importing-external-issues/importing-third-party-issues/) on importing third-party issues
