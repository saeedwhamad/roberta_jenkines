pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
             git https://github.com/saeedwhamad/roberta_jenkines/tree/main/roberta
             sh '''
            docker login -u "saeedwh" -p "sa22edhama"
            docker image build -t roberta:${BUILD_NUMBER} .
            docker tag -t roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
            docker push saeedwh/roberta:${BUILD_NUMBER}
            echo hi
                   '''
                }
            }
        }
    }
