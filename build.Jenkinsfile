pipeline {
    agent {
        docker {
            image 'saeedwh/jenkinsagent:latest'
            args '--user root -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    stages{
        stage('Build') {
            steps {

                   sh '''
                    docker login -u saeedwh -p sa22edhama
                    docker image build -t roberta:${BUILD_NUMBER} .
                    docker tag roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
                    docker push saeedwh/roberta:${BUILD_NUMBER}
                      '''
            }

        }
     }
}
