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
