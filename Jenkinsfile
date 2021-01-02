pipeline {
	//agent any
	agent {
		docker {
			image 'maven:3.6.3'
		}
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Tests"
			}
		}
		stage('Integration Tests') {
			steps {
				echo "Integration Tests"
			}
		}
	} 
	post {
		always {
			echo 'Im awesom. I run always.'
		}
		success {
			echo 'I run when you are successful. HA HA HA'
		}
		failure {
			echo 'I run when you fail.'
		}
	}
}