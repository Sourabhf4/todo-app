pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Sourabhf4/todo-app.git'
            }
        }
        stage('Build Image') {
            steps {
                script {
                    def imageName = "todoapp-image-${BUILD_NUMBER}"
                    sh "docker build -t ${imageName} ."
                }
            }
        }
        stage('Run Container') {
            steps {
                script {
                    def imageName = "todoapp-image-${BUILD_NUMBER}"
                    def containerName = "todoapp-container-${BUILD_NUMBER}"
                    sh "docker run -d --name ${containerName} -P ${imageName}"
                }
            }
        }
    }
}
