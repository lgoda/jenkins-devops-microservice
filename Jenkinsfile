pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Tests') {
			steps {
				sh "mvn failsafe:inegration-test failsafe:verify"
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