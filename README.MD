# API client for Blog Post spring boot rest service

## The API client code is generated using OpenAPI Generator (https://openapi-generator.tech/)

### To be able to generate the client code we have to generate OpenAPI specification

1. Follow https://springdoc.org/ to generate OpenAPI specification for your Spring Boot project

### Project structure

Api client project contains only 3 files needed to generate client.

- `pom.xml` - contains configuration of openapi-generator-maven-plugin and clean-maven-plugin
- `.gitignore` - blocks possibility to commit and push generated code to repository
- `.yaml` or `.json` file with OpenApi Specification as base for client generation
- `README.MD` - project description

### Client generation flow

- On each 'mvn clean' phase all generated code is removed.
- Run: 
  ```shell
  $ mvn clean compile
  ```
  - On `generate-sources` phase (so, before compile) openapi-generator-maven-plugin is executed with `generate` goal.
  - Note: Direct execution via plugin will not work (https://github.com/OpenAPITools/openapi-generator/issues/2207)
- OpenAPI Generator https://openapi-generator.tech/docs/generators/java generates Java source code for API client from
  json/yaml including model and client.

Scope of generation (model, clients) and configuration for file names, packages, etc. can be found in `pom.xml` inside `openapi-generator-maven-plugin` plugin