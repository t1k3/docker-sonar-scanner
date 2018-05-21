# Sonar Scanner Docker

## Requirements
* SonarQube Server
* `sonar-project.properties` in `project` path

## Usage
```bash
$ docker-compose -p <projectname> up -d
$ docker-compose -p <projectname> run --rm sonar-scanner
```

## sonar-project.properties example
```sonar-project.properties
# Required metadata
sonar.projectKey=<projectKeyFrom localhost:9000>
sonar.projectName=<Projectname>
sonar.projectVersion=0.1

# Project directory
sonar.projectBaseDir=/var/www/html

# Path to the parent source code directory.
sonar.sources=app

# Language
# We've commented this out, because we want to analyse both PHP and Javascript
sonar.language=php

# Encoding of the source code
sonar.sourceEncoding=UTF-8

# Reusing PHPUnit reports
sonar.php.tests.reportPath=reports/phpunit.junit.xml
sonar.php.coverage.reportPaths=reports/phpunit.coverage.xml
sonar.coverage.exclusions=tests/**/*.php

# Here, you can exclude all the directories that you don't want to analyse.
# As an example, I'm excluding the Providers directory
sonar.exclusions=vendor/**

# Additional parameters
#sonar.my.property=value

# Host
sonar.host.url=http://localhost:9000

```
