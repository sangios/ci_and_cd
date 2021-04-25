pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
				echo 'Branch name: ' + env.BRANCH_NAME
	            sh 'fastlane build_app'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}