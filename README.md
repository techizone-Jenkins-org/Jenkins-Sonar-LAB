# SonarQube Installation

####  Installation of openJDK
## Amazon Linux
```
sudo dnf update -y
sudo yum install java-17-amazon-corretto-devel -y
``` 

####  Create sonar User
```
sudo useradd -r sonar 
```
####  Give sudo permission for "sonar"  User
```
 sudo visudo
Add the below line and Save.
		sonar   ALL=(ALL)       NOPASSWD: ALL
``` 

#### Download and Install Tomcat
```
sudo wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.2.77730.zip -P /opt
sudo unzip /opt/sonarqube-9.9.2.77730.zip -d /opt
sudo mv /opt/sonarqube-9.9.2.77730 /opt/sonar
```
#### Configure Permissions
```
chown -R sonar:sonar /opt/sonar/
chmod -R 775 /opt/sonar/
```

#### Start/Stop Manually
```
su - sonar
cd /opt/sonar/bin/linux-x86-64/
./sonar.sh start
./sonar.sh shutdown
```

#### Create Service File
**sudo vi /etc/systemd/system/sonarqube.service**

```
[Unit]
Description=SonarQube service
After=syslog.target network.target
				
[Service]
Type=forking
User=sonar
Group=sonar
PermissionsStartOnly=true
#ExecStart=/bin/nohup /opt/java/bin/java -Xms32m -Xmx32m -Djava.net.preferIPv4Stack=true -jar /opt/sonar/lib/sonar-application-9.0.jar
ExecStart=/opt/sonar/bin/linux-x86-64/sonar.sh start
ExecStop=/opt/sonar/bin/linux-x86-64/sonar.sh stop
StandardOutput=syslog
LimitNOFILE=131072
LimitNPROC=8192
TimeoutStartSec=5
Restart=always
SuccessExitStatus=143
				
[Install]
WantedBy=multi-user.target
```

#### Reload Systemd and enable tomcat
```
sudo systemctl daemon-reload
sudo systemctl enable sonarqube
sudo systemctl start sonarqube
```
# SonarQube Configuration

Open Browser hit <IP>:9000

#### Enable User Authentication
```
Step:1 ===> on your web browser, login as "admin" user
Step:2 ===> go to Administration ===> Security ===> you have an option "Force user authentication"

			By default these Option is Disable we have to Enable that Option and Save
```





