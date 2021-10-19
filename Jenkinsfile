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
                sh 'echo hello world 2'
            }
        }
    }
}
    post{
        always{
            slackSend channel: '#random', message: 'haii'
        }
    }