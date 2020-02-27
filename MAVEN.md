### Apache Maven Cheat Sheet
#### Building
* Building a package
  `mvn clean package`
* Installing into local repository
  `mvn install`
* Skipping the tests
  `mvn install -DskipTests`
#### Deploying
* Deploying an artifact
  `mvn deploy`
* Releasing an artifact
  `mvn release:prepare`
  `mvn release:perform`
  `mvn release:clean`
  `mvn release:rollback`
#### POM maintenance
* Clean up / tidy the POM
  `mvn tidy:pom`
* Set project and submodule version
  `mvn versions:set -DnewVersion=1.0.3-SNAPSHOT`
* Show dependency updates
  `mvn versions:display-dependency-updates`
* Show plugin updates
  `mvn versions:display-plugin-updates`
