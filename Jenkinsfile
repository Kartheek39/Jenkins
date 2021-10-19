//pipeline {
//    agent none
////    agent {
////        node {
////            label 'WORKSTATION'
////        }
////    }
//    options { disableConcurrentBuilds() }
//
//    tools {
//        maven 'maven'
//    }
//    parameters {
//        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//
//        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//
//        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//
//        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//
//        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//    }
//    environment{
//        SAMPLE_URL = "google.com"
//        SLACK_TOKEN = credentials"slack"
//    }
//    stages {
//        stage('one') {
//            agent {
//                node {
//                    label 'NODEJS'
//                }
//            }
//            input {
//                message "Should we continue?"
//                ok "Yes, we should."
//                //submitter "alice,bob"
//                parameters {
//                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                }
//            }
//            steps {
//                sh 'echo hello world'
//                sh 'echo ${SAMPLE_URL}'
//                sh 'echo ${SLACK_TOKEN}'
//            }
//        }
//        stage('two'){
//            when {
//                environment name: 'SAMPLE_URL', value: 'yahoo'
//            }
//            agent {
//                node {
//                    label 'JAVA'
//                }
//            }
//            environment{
//                SAMPLE_URL = "yahoo.com"
//            }
//            steps{
//                sh 'echo hello world 2'
//                sh 'echo ${SAMPLE_URL}'
//            }
//        }
//    }
//
//    post{
//        success{
//            slackSend channel: '#random', color: 'good', message: 'success'
//        }
//        failure{
//            slackSend channel: '#random', color: 'danger', message: 'failure'
//        }
//    }
//}

pipeline{
    agent any
    stages{
        stage('seq1'){
            steps{
                sh 'echo hello'
            }

        }
        stage('par1'){
            parallel{
                stage('p1'){
                    steps{
                        sh 'sleep 20'
                    }
                }
                stage('p2'){
                    steps{
                        sh 'sleep 50'
                    }
                }
                stage('p3'){
                    steps{
                        sh 'sleep 80'
                    }
                }
            }
        }
        stage('par2'){
            parallel{
                stage('p1'){
                    steps{
                        sh 'sleep 20'
                    }
                }
                stage('p2'){
                    steps{
                        sh 'sleep 50'
                    }
                }
                stage('p3'){
                    steps{
                        sh 'sleep 80'
                    }
                }
            }
        }
        stage('seq2'){
            steps{
                sh 'echo hello'
            }
        }

    }
}