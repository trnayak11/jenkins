pipeline{
	agent none
	stages{
		stage('pull'){
				steps {
					git credentialsId: 'github', url: 'https://github.com/trnayak11/devopsJava.git'
				}
			}
		stage('codeAnalsis'){
				steps {
					def mvnHome = tool name: 'mvn'
					withSonarQubeEnv('sonar') {
						sh "${mvnHome}/bin/mvn sonar:sonar"
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
