pipeline {
    agent any

    stages {
        stage('Build') {
            steps {

                sh '''
                    docker build -t roberta:${BUILD_NUMBER} /roberta/
                '''

                withCredentials([usernamePassword(credentialsId: 'docker-hub', usernameVariable: 'saeedwh', passwordVariable: 'sa22edhama')]) {
                    sh '''
                        docker login -u $usernameVariable -p $usernamePassword
                        docker tag roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
                        docker push saeedwh/roberta:${BUILD_NUMBER}
                    '''
                }
            }
        }
    }
}
