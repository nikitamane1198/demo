pipeline {
    agent any

    stages {
        stage('Build Image') {
            steps {
                script {
                    dockerImage = docker.build("housing-price-prediction")
                }
            }
        }
        stage('Publish Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'nikita321123') {
                        dockerImage.push('latest')
                    }
                }
            }
        }
    }
}
