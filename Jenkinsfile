  pipeline {
    agent any
     tools {
       maven "maven"
     }
       stages{

  stage('CheckOutCode'){
    steps{
    git 'https://github.com/narendramarolix/jenkinsrepo11.git'
	}
  }
	       stage(build){
		       steps{
		      sh "mvn clean package"
	       }
		       
       }
  }
  }




