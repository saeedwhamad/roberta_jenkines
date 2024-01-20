pipeline {
    agent {
       docker {
        image 'https://hub.docker.com/layers/saeedwh/jenkinsagent/latest/images/sha256-7f8592fc9ea1ffec3fe482c186d98e0bfaf792d8e94ba294d25db8719adf14ec?context=repo'
        args  '--user root -v /var/run/docker.sock:/var/run/docker.sock'
    }
}

    stages {
        stage('Build') {
            steps {

             sh '''
            docker login -u saeedwh -p sa22edhama
            docker image build -t roberta:${BUILD_NUMBER} .
            docker tag roberta:${BUILD_NUMBER} saeedwh/roberta:${BUILD_NUMBER}
            docker push saeedwh/roberta:${BUILD_NUMBER}
            echo change
                   '''
                }
            }
        }
    }
