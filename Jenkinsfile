

pipeline {
   
    agent any
  environment{
     DOCKERHUB_CREDENTIALS=credentials('dockerhub_zainabzafar23')
  }
    stages{
        stage('Build'){
            steps{
                bat 'npm install'

            }
        }
        stage('test'){
            steps{
                bat 'echo "Test is running"'
            }
        }
        stage('Docker build'){
            steps{
                bat 'docker build -t zainabzafar23/jenkins-integration:latest .'
            }
        }
        stage('login'){
            steps{
                bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push'){
            steps{
                bat 'docker push zainabzafar23/jenkins-integration:latest'
            }
        }
        stage('deploy'){
            steps{
                bat 'echo "Deploying the application"'
            }
        } 
    }
}
