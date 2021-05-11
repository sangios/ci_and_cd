pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo 'Branch name: ' + env.BRANCH_NAME
                sh '''
                pwd
                cd StudyCICD
                fastlane build_ci_cd_app
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh '''
                pwd
                cd StudyCICD
                fastlane run_unittest
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh '''
                pwd
                cd StudyCICD
                fastlane code_coverage
                '''
            }
        }
    }
}