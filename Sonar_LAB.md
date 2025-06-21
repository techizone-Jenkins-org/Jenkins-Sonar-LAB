LAB:2 ==> Generate Sonar Report without edit POM.xml
=====================================================


Step:1 ===> Create token in SonarQube server

	Sonar web page ==> Administration ==> security ==> Click on user ==> Click on Token


Step:2 ==> By passing sonar parameters to your Maven command

	1. open pom.xml ===> goto <properties> and mention below details
```
mvn clean verify sonar:sonar \
  -Dsonar.projectKey=<Your-Sonar-ProjectKEY> \
  -Dsonar.host.url=<Your-Sonar-URL> \
  -Dsonar.login=<Your-Sonar-Token>
```


LAB:2 ==> Generate Sonar Report By editing POM.xml
==============================================


Step:1 ===> Create token in SonarQube server

	Sonar web page ==> Administration ==> security ==> Click on user ==> Click on Token


Step:2 ==> Integrate SonarQube with Maven

	1. open pom.xml ===> goto <properties> and mention below details
```
<properties>
	<sonar.host.url>Your-Sonar-URL</sonar.host.url>
	<sonar.login>Sonar-Username</sonar.login>
	<sonar.password>Sonar-Token</sonar.password>
</properties>
```
