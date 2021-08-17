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
        stage('Push Docker Image') {
            
            steps {
                input 'Deploy to Production?'
                milestone(1)
            }
        }
        stage('DeployToProduction') {
            
            steps {
                echo 'Running build automation3' 
            }
        }
    }
}

