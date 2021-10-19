pipeline {
    agent none
//    agent {
//        node {
//            label 'WORKSTATION'
//        }
//    }
    stages {
        stage('one') {
            agent {
                node {
                    label 'NODEJS'
                }
            }
            steps {
                sh 'echo hello world'
            }
        }
        stage('two'){
            agent {
                node {
                    label 'JAVA'
                }
            }
            steps{
                sh 'echo0 hello world 2'
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
