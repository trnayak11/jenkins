pipeline{
	agent none
	stages{
		stage('pull'){
				steps {
					echo 'pulling the code'
				}
			}
		stage('build'){
				steps {
					echo 'building the code'
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
