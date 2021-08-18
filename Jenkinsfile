pipeline {
    agent any
    environment {
        DOCKER_IMAGE_NAME = "ridgesidenetworks/train-schedule"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
            }
        }
        stage('Send Approval Email') {
            steps {
                emailext attachLog: true, body: 'New Application requires your approval', subject: 'Test CICD Build subject', to: 'markf6@gmail.com'
            }
        }
        stage('Approval') {
            
            steps {
                input 'Deploy to Production?'
                milestone(1)
                 
            }
        }
        stage('DeployToProduction') {
            
            steps {
                echo 'Deploying to Production'
            }
        }
    }
}
