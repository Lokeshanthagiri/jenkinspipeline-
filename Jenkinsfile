pipeline {
    agent any
    environment {
        IMAGE_NAME = 'anthagirilokesh/my-python-app'
    }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME .'
                }
            }
        }

        stage('Test App') {
            steps {
                echo 'Running tests (placeholder)...'
                sh 'echo "No tests yet!"'
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password', variable: 'DOCKERHUB_PASS')]) {
                    sh "echo $DOCKERHUB_PASS | docker login -u yourdockerhubusername --password-stdin"
                    sh 'docker push $IMAGE_NAME'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution complete.'
        }
    }
}
