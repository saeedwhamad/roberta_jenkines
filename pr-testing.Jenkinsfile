pipeline {
    agent any

    stages {
        stage('Unittest') {
            steps {
                python3 -m pytest --junitxml results.xml tests
                post {
                      always {
                           junit allowEmptyResults: true, testResults: 'results.xml'
                              }
                          }

            }
        }
        stage('Lint') {
            steps {
                echo "linting"
                echo "change !!!"
            }
        }
        stage('Functional test') {
            steps {
                echo "testing"
            }
        }
    }
}