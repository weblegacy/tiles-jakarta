# Tiles-Jakarta-Servlet

Copy of

* [Apache Tiles 2.2.2 Servlet](https://github.com/apache/tiles/tree/tiles-2.2.2/tiles-servlet)
* [Apache Tiles 2.2.2 Servlet Wildcard](https://github.com/apache/tiles/tree/tiles-2.2.2/tiles-servlet-wildcard)

adapted for jakarata-servlet (EE9+) and extends with JPMS.

For documentation see [https://weblegacy.github.io/tiles-jakarta](https://weblegacy.github.io/tiles-jakarta).

## Versions-Overview

| Version     | JEE-Version  | Java-Version | Servlet | JSP | EL  | JSF | JSTL |
|------------:|-------------:|-------------:|--------:|----:|----:|----:|-----:|
| 1.0.0 - WiP | Jakarta EE 9 |            8 |     5.0 | 3.0 | 4.0 | 3.0 |  2.0 |

## Building Tiles-Jakarta

### Prerequisites

* Apache Maven 3.9.0\+
* JDK 9\+

### MAVEN-Profiles

* **release** - Signs all of the project's attached artifacts with GnuPG

### Building-Steps

1. Clean full project  
   `mvn clean`
2. Build and test project
   * with tests  
     `mvn verify`
   * to skip tests  
     add `-DskipTests` for example `mvn  -DskipTests verify`
3. Generate site-documentation  
   `mvn site site:stage`  
4. Publish site-documentation  
   1. `mvn clean site site:stage`
   2. `mvn scm-publish:publish-scm`
5. Generate Assemblies  
   `mvn package`
6. Deploy all artifacts to `Central-Repo`  
   * `mvn deploy` for SNAPSHOTs
   * `mvn -Prelease clean deploy` for releases

### Support runs

* Set version number  
  `mvn versions:set -DnewVersion=...`
* Dependency Report  
  `mvn versions:display-dependency-updates versions:display-plugin-updates versions:display-property-updates`
