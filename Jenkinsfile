pipeline{
	agent any
	tools {
		name: 'mvn'
		type: 'maven'
		
	}
	stages{
		stage('pull'){
				steps {
					checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/trnayak11/devopsJava.git']]])
				}
			}
		
		stage('build'){
				steps {
					sh 'mvn clean' 
				}
			}
		}
	}
