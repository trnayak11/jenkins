pipeline{
	agent any
	tools {
		maven 'mvn'
		
	}
	stages{
		stage('pull'){
				steps {
					git credentialsId: 'github', url: 'https://github.com/trnayak11/devopsJava.git'
				}
			}
		
		stage('build'){
				steps {
					sh 'mvn clean install -f pom.xml' 
				}
			}
		}
		post {
			always {
				echo 'always execute'
			}
			success {
				echo 'suceeded'
			}
			failure {
				echo 'failed'
			}
		}
	}
