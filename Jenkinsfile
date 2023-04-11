pipeline {  
    agent any  
        stages {  
       	   //Code starts for stage Cleaning
        stage('Clean') {
            steps {
                sh 'mvn clean'
            }
        }
		//Code ends for stage Clean

//Code starts for stage Compile
		stage('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
		//Code ends for stage Compile
		
		
		//Code starts for stage Code Analysis
		stage('Code Analysis') {
            steps {
			 script {
          scannerHome = tool 'sonarscanner'
        }
				withSonarQubeEnv('Sonarqubefirstproject')
				{
				sh "${scannerHome}/bin/sonar-scanner"
				}
			}
		}
		//Code ends for stage Code Analysis
        }
}
