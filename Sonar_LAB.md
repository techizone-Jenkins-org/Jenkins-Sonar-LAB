LAB:1 ==> GET .war App Reports from SonarQube
==============================================


Step:1 ===> Create token in SonarQube server

	Sonar web page ==> Administration ==> security ==> Click on user ==> Click on Token


Step:2 ==> Integrate SonarQube with Maven

	1. open pom.xml ===> goto <properties> and mention below details
	
<properties>
	<sonar.host.url>Your-Sonar-URL</sonar.host.url>
	<sonar.login>Sonar-Username</sonar.login>
	<sonar.password>Sonar-Token</sonar.password>
</properties>
