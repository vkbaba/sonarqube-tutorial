# sonarqube-tutorial
The purpose of this tutorial is to get started with static code analysis by SonarQube without writing any codes.   
This tutorial uses Katacoda, so you do not need to prepare Kubernetes clusters.   
https://www.katacoda.com/courses/cicd/sonarqube   
   
1. Complete Step 1-3 
1. Download and unzip sonnar-scanner (See https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/)  
```wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.5.0.2216-linux.zip```   
```unzip sonar-scanner-cli-4.5.0.2216-linux.zip```   
1. Clone this repo and cd   
```git clone https://github.com/vkbaba/sonarqube-tutorial.git```   
```cd sonarqube-tutorial```   
1. Get a html file you want to scan   
```wget http://abehiroshi.la.coocan.jp/top.htm -O top.html```   
1. Run sonnar-scanner   
```NODE_IP=`kubectl get node node01 -o jsonpath={.status.addresses[].address}` ```   
```../sonar-scanner-4.5.0.2216-linux/bin/sonar-scanner -Dsonar.host.url=http://$NODE_IP:31111 -Dproject.settings=./sonar-project.properties```   
1. Access SonarQube Dashboard


