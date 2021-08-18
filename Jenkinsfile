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
                mail bcc: '', body: '''#${env.BUILD_NUMBER} is being deployed and requires ITSG-22 Security tag review.  Please review the following YML file and approve the ITSG-22 Tag assignments

https://github.com/ridgesidenetworks/CN-SeriesDemo/blob/main/guestbook.yml''', cc: '', from: '', replyTo: '', subject: 'ITSG-22 Tag approval', to: 'markf6@gmail.com'
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
