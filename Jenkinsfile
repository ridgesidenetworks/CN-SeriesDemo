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
        stage('Build Docker Image') {
            
            steps {
                echo 'Running build automation2'             
            }
        }
        stage('Approval') {
            
            steps {
                input {
                message "Should we continue?"
                ok "Yes"
                }
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
