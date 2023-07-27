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
	       
	stage('ExecuteSonarQubeReport'){
  steps{
  sh  "mvn clean package sonar:sonar"
  }
  }

  

  stage('DeployAppIntoTomcat'){
  steps{
  sshagent(['82296555-1009-4641-ac88-3ed00d51be83']) {
   sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/narendra2/target/vprofile-0.0.1.war ec2-user@18.117.181.32:/opt/apache-tomcat-9.0.78/webapps/"    
  }
  }
  }
stage('UploadArtifactsIntoNexus'){
  steps{
  sh  "mvn clean deploy"
  }
  }

       
  }
  }





