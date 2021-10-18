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
                    label 'WORKSTATION'
                }
            }
            steps {
                sh 'echo hello world'
            }
        }
        stage('two'){
            agent {
                node {
                    label 'WORKSTATION'
                }
            }
            steps{
                sh 'echo hello world 2'
            }
        }
    }
}