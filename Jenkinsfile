pipeline {
	agent any
	tools {
		nodejs 'NodeJS'
	}
	stages {
		stage('Checkout Github'){
			steps {
				git branch: 'main', credentialsId: 'jen-doc-git', url: 'https://github.com/dillibabu1415/NodeApp-poc3.git'
			}
		}		
		stage('Install node dependencies'){
			steps {
				sh 'npm install'
			}
		}
		stage('Test Code'){
			steps {
				sh 'npm test'
			}
			post {
		success {
			echo 'Build completed succesfully!'
		}
		failure {
			echo 'Build failed. Check logs.'
		}
	}
   }
 }
}
