pipeline {
    agent any
    options{
        buildDiscarder(logRotator(numToKeepStr: '2', artifactNumToKeepStr: '2'))
    }
    stages {
        stage('Build') {         
            steps {
                requestApproval(environment: 'DEV', time: 1, unit: 'DAYS')
                sayHello 'Mark'
                echo 'Building..'
            }
        }
        stage('Test') {
            when{
                allOf{
                    branch 'main'
                    changeset "api/*"
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('JS Test') {       
            agent { 
                docker { image 'node:18' }
            }  
            steps {
                dir('javascript'){
                    script{
                        sh 'npm start'
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
