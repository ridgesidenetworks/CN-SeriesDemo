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
                input 'Deploy to Production?'
                milestone(1)
                echo 'Deploying to Production' 
            }
        }
        stage('DeployToProduction') {
            
            steps {
                kubernetesDeploy(
                    kubeconfigId: 'kubeconfig',
                    configs: 'guestbook.yml',
                    enableConfigSubstitution: true
                )
            }
        }
    }
}
