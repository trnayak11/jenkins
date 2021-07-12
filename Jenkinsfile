pipeline{
	agent any
	tools {
		maven 'mvn'
	}
	stages{
		stage('pull'){
				steps {
					checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/trnayak11/devopsJava.git']]])
				}
			}
		
		stage('codeQuality'){
				steps {
					withSonarQubeEnv('sonar'){
					bat 'mvn sonar:sonar' 
				}
			}
		}
		stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
            }
          }
		
		stage('build'){
				steps {
					bat 'mvn clean install' 
				}
			}
	    
	}
}
