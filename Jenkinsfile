pipeline{
    agent {
        docker {
            image 'node:18.17.1-alpine3.18'
        }
    }

    environment {
    FIREBASE_DEPLOY_TOKEN = credentials('firebase-token')
    }

    stages{
        stage('Building'){
            steps{
            sh 'npm install -g firebase-tools'
            }
        } 

         stage('Testing'){
            steps{
            sh 'firebase deploy -P testing-lab11-devops-denis --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }

        stage('Staging'){
            steps{
            sh 'firebase deploy -P staging-lab11-devops-denis --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }

        stage('Production'){
            steps{
            sh 'firebase deploy -P production-lab11-devops-denis --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }
    }
}
