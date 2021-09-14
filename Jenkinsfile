pipeline {
	agent any
	// agent {docker {image 'maven:3.6.3'} }
	environment {
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				echo "Build"
				sh 'mvn --version'
				sh 'docker --version'
			}
		}

		stage('Test') {
			steps {
				echo "Test"
			}
		}

		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	}
	post {
		always {
			echo 'I run always'
		}

		success {
			echo 'I run at success'
		}

		failure {
			echo 'I run at fail'
		}
	}
}
