pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
	            fastlane custom_lane
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