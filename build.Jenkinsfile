pipeline {
    agent any

     environment {
        DOCKER_REGISTRY = 'docker.io'
    }

    stages {
        stage('Build') {
            steps {
                   sh '''
            docker login -u saeedwh -p sa22edhama ${DOCKER_REGISTRY}
            docker build -t roberta:${env.BUILD_ID} .
            docker tag roberta:${env.BUILD_ID} ${DOCKER_REGISTRY}/roberta:${env.BUILD_ID}
            docker push ${DOCKER_REGISTRY}/roberta:${env.BUILD_ID}
       '''

            }
        }
    }
}