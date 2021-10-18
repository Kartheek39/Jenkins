pipeline {
    agent {
        node {
            label 'WORKSTATION'
        }
    }
    stages {
        stage('one') {
            steps {
                sh 'echo hello world'
            }
        }
        stage('two'){
            steps{
                sh 'echo hello world 2'
            }
        }
    }
}