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
    post{
        success{
            setBuildStatus("Build succeeded", "SUCCESS");
        }

        failure {
            setBuildStatus("Build failed", "FAILURE");
        } 
    }
}

void setBuildStatus(String message, String state) {
    step([
        $class: "GitHubCommitStatusSetter",
        reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://webhook.socketxp.com/sangnguyen-mamnkcsh"],
        contextSource: [$class: "ManuallyEnteredCommitContextSource", context: "ci/jenkins/build-status"],
        errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
        statusResultSource: [$class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]]]
    ]);
}