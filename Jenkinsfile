pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                echo 'git checkout'
                git url:'https://github.com/Sourabhf4/todo-app.git' , branch:'main'
            }
        }
        stage('test') {
            steps {
                echo 'run testcases'
            }
        }
        stage('build ') {
            steps {
                echo 'Hello World'
                sh 'docker build -t todo:todo-${BUILD_NUMBER} .'
            }
        }
        stage('deploy') {
            steps {
                echo 'this is deployment stage'
                sh 'docker run -d --name todo-${BUILD_NUMBER} -P todo:todo-${BUILD_NUMBER} '
            }
        }
    }
}
