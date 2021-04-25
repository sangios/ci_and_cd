pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
	            sh 'fastlane custom_lane'
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