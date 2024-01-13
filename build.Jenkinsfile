pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                 sh '''
            docker login -u "saeedwh" -p "sa22edhama"
            docker build -t roberta:${BUILD_NUMBER} .
            docker tag -t roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
            docker push saeedwh/roberta:${BUILD_NUMBER}
            echo hi
                   '''
                }
            }
        }
    }
