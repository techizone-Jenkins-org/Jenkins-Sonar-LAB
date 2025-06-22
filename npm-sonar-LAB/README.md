# nodejs-app-Sonar-LAB

## Install Node

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
. ~/.nvm/nvm.sh
nvm install 16

node -v
npm -v
```

To start this application first you can get this repo code using below url
#### Clone the Repo
```
git clone https://github.com/techizone-Jenkins-org/Jenkins-Sonar-LAB.git

cd Jenkins-Sonar-LAB/npm-sonar-LAB
```
#### Download the Dependencies
```
npm install
```
#### Start the Application
```
node app.js

(OR) 

npm start
```
To execute Test cases, we will run the below command

```
npm test
```

To Execute the SonarQube Repor, execute the below command.
```
npm run sonar

(OR) 

node sonar-project.js
```

