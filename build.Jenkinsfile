pipeline {
    agent any


    stages {
        stage('Build') {
            steps {
            git ‘https://github.com/saeedwhamad/roberta_jenkines/tree/main/roberta’
            sh '''
            docker build -t roberta:${BUILD_NUMBER} .
            withCredentials([usernamePassword(credentialsId: ‘docker-hub’, usernameVariable: ‘saeedwh’, passwordVariable: ‘sa22edhama’)])

           docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD

            docker tag roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
            docker push saeedwh/roberta:${BUILD_NUMBER}
              '''

            }
        }
    }
}
