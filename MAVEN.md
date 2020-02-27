### Apache Maven Cheat Sheet

#### Building
* Building a package<br/>
  `mvn clean package`
* Installing into local repository<br/>
  `mvn install`
* Skipping the tests<br/>
  `mvn install -DskipTests`
  
#### Deploying
* Deploying an artifact<br/>
  `mvn deploy`
* Releasing an artifact<br/>
  `mvn release:prepare`
  `mvn release:perform`
  `mvn release:clean`
  `mvn release:rollback`
  
#### POM maintenance
* Clean up / tidy the POM ([more](https://www.mojohaus.org/tidy-maven-plugin/))<br/>
  `mvn tidy:pom`
* Set project and submodule version ([more](https://www.mojohaus.org/versions-maven-plugin/examples/set.html))<br/>
  `mvn versions:set -DnewVersion=1.0.3-SNAPSHOT`
* Show dependency updates ([more](https://www.mojohaus.org/versions-maven-plugin/display-dependency-updates-mojo.html))<br/>
  `mvn versions:display-dependency-updates`
* Show plugin updates ([more](https://www.mojohaus.org/versions-maven-plugin/examples/display-plugin-updates.html))<br/>
  `mvn versions:display-plugin-updates`
