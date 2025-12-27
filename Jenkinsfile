node
{
def mavenHome = tool name: 'maven3.9.12'     

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckOutCode'){
git branch: 'development', credentialsId: 'ea0914f1-644d-4bec-991a-86f3879118bb', url: 'https://github.com/ysekhon1/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

/*
stage('ExecuteSonarQubeReport') {
//sh "${mavenHome}/bin/mvn sonar:sonar"        
    }

stage('UploadArtifactIntoNexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}

stage('DeployAppintotomcat'){
sshagent(['TomcatServerCredentials']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.1.72:/opt/apache-tomcat-9.0.112/webapps/"
}
}
*/

}
