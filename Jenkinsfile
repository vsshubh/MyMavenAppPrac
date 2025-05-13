pipeline {
	agent any
	
	tools {
		maven 'MAVEN'
	}
	
	stages {
		stage('Checkout') {
			steps {
				git branch : 'master', url: 'https://github.com/vsshubh/MyMavenAppPrac.git'
			}
		}
		
		stage('Build') {
			steps {
				sh 'mvn compile package'
			}
		}
		
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}
		
		stage('Run Application') {
			steps {
				sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
			}
		}
	}
	
	post {
		success {
			echo 'Build and deployment successfull'
		}
		failure {
			echo 'Build failed'
		}
	}			
}
