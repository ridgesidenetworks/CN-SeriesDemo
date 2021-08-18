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
                emailext body: '''The following application review requires ITSG-22 Code review and approval: https://github.com/ridgesidenetworks/CN-SeriesDemo/blob/main/guestbook.yml

Please click the following link to approve the job:  http://10.0.0.50:8080/job/EmailTest/

''', subject: 'New application deployed requires ITSG-22 Tag Review', to: 'mallen@paloaltonetworks.com'
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
