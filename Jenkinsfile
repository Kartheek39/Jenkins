pipeline {
    agent none
//    agent {
//        node {
//            label 'WORKSTATION'
//        }
//    }
    environment{
        SAMPLE_URL = "google.com"
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
            }
        }
        stage('two'){
            agent {
                node {
                    label 'JAVA'
                }
            }
            steps{
                sh 'echo hello world 2'
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
