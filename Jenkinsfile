  pipeline {
    agent any
     tools {
       maven "maven"
     }
       stages{

  stage('CheckOutCode'){
    steps{
    git branch: 'main', url: 'https://github.com/narendramarolix/jenkinsrepo11.git'
	}
  }
	       stage(build){
		       steps{
		      sh "mvn clean package"
	       }
		       
       }
	       /*
	stage('ExecuteSonarQubeReport'){
  steps{
  sh  "mvn clean package sonar:sonar"
  }
  }

  stage('UploadArtifactsIntoNexus'){
  steps{
  sh  "mvn clean deploy"
  }
  }
*/
  stage('DeployAppIntoTomcat'){
  steps{
  sshagent(['ssh']) {
   sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/narendra2/target/vprofile-v2.war ec2-user@18.117.181.32:/opt/tomcat/webapps/"    
  }
  }
  }


       
  }
  }





