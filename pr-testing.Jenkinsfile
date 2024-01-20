pipeline {
    agent any

    stages {
        stage('Unittest') {
            steps {
               sh 'python3 -m pytest --junitxml results.xml tests'
               echo hi
               }
                post {
                      always {
                           junit allowEmptyResults: true, testResults: 'results.xml'
                              }
                }


        }
        stage('Lint') {
            steps {
                  sh 'python3 -m pylint -f parseable --reports=no *.py > pylint.log'
                        }
                        post {
                          always {
                            sh 'cat pylint.log'
                            recordIssues (
                              enabledForFailure: true,
                              aggregatingResults: true,
                              tools: [pyLint(name: 'Pylint', pattern: '**/pylint.log')]
                            )
                          }
                        }
        }
        stage('Functional test') {
            steps {
                echo "testing"
            }
        }
    }
}