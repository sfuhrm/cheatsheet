### Apache Maven Cheat Sheet

#### Building
* Building a package<br/>
  `mvn clean package`
* Installing into local repository<br/>
  `mvn install`
* Skipping the tests<br/>
  `mvn install -DskipTests`
  
#### Code Quality
* Generating the PMD report ([more](https://maven.apache.org/plugins/maven-pmd-plugin/))<br/>
  `mvn pmd:pmd`
* Generating the FindBugs report ([more](https://gleclaire.github.io/findbugs-maven-plugin/usage.html))<br/>
  `mvn findbugs:findbugs`
  
#### Deploying
* Deploying an artifact<br/>
  `mvn deploy`
* Releasing an artifact<br/>
  `mvn release:prepare`<br/>
  `mvn release:perform`<br/>
* Rolling back a released artifact<br/>
  `mvn release:rollback`
* Cleaning up release data<br/>
  `mvn release:clean`<br/>
* Install JAR without POM as artifact to Maven cache<br>
  `mvn install:install-file -Dfile=<path-to-file> -DgroupId=<group-id> -DartifactId=<artifact-id> -Dversion=<version> -Dpackaging=<packaging> -DgeneratePom=true`

#### File maintenance
* Set license header to all files ([more](http://www.mojohaus.org/license-maven-plugin/update-file-header-mojo.html))<br/>
  `mvn -Dproject.inceptionYear=2020 -Dlicense.licenseName=apache_v2 license:update-file-header`

#### POM maintenance
* XML indent all POMs with 2 spaces<br/>
  `for POM in $(find -name pom.xml); do echo $POM; (xmlstarlet fo < $POM > x && mv x $POM); done`
* Clean up / tidy the POM ([more](https://www.mojohaus.org/tidy-maven-plugin/))<br/>
  `mvn tidy:pom`
* Set project and submodule version ([more](https://www.mojohaus.org/versions-maven-plugin/examples/set.html))<br/>
  `mvn versions:set -DnewVersion=1.0.3-SNAPSHOT`
* Show dependency tree<br/>
  `mvn dependency:tree`
* Analyse unused / undeclared dependencies<br/>
  `mvn dependency:analyze`
* Show dependency updates ([more](https://www.mojohaus.org/versions-maven-plugin/display-dependency-updates-mojo.html))<br/>
  `mvn versions:display-dependency-updates`
* Show plugin updates ([more](https://www.mojohaus.org/versions-maven-plugin/examples/display-plugin-updates.html))<br/>
  `mvn versions:display-plugin-updates`
