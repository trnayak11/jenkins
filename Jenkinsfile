pipeline{
	agent none
	stages{
		stage('pull'){
				steps {
					git credentialsId: 'github', url: 'https://github.com/trnayak11/devopsJava.git'
				}
			}
		stage('codeAnalsis'){
				environment {
					scannerHome = tool 'sonar'
				}
				steps {
						withSonarQubeEnv('sonarqube') {
							sh "${scannerHome}/bin/sonar-scanner"
						}
				}
			}
		stage('push'){
				steps {
					echo 'pushing the code'
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
