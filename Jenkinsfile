pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
				echo 'Branch name: ' + env.BRANCH_NAME
				sh 'pwd'
				sh 'cd StudyCICD'
				sh 'pwd'
	            sh 'fastlane build_ci_cd_app'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
				sh 'cd StudyCICD'
				sh 'pwd'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
				sh 'cd StudyCICD'
				sh 'pwd'
            }
        }
    }
}