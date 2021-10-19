pipeline {
    agent none
//    agent {
//        node {
//            label 'WORKSTATION'
//        }
//    }
    options { disableConcurrentBuilds() }
    environment{
        SAMPLE_URL = "google.com"
        SLACK_TOKEN = credentials"slack"
    }
    stages {
        stage('one') {
            agent {
                node {
                    label 'NODEJS'
                }
            }
            steps {
                sh 'echo hello world'
                sh 'echo ${SAMPLE_URL}'
                sh 'echo ${SLACK_TOKEN}'
            }
        }
        stage('two'){
            agent {
                node {
                    label 'JAVA'
                }
            }
            environment{
                SAMPLE_URL = "yahoo.com"
            }
            steps{
                sh 'echo hello world 2'
                sh 'echo ${SAMPLE_URL}'
            }
        }
    }

    post{
        success{
            slackSend channel: '#random', color: 'good', message: 'success'
        }
        failure{
            slackSend channel: '#random', color: 'danger', message: 'failure'
        }
    }
}
