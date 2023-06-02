pipeline {
    agent any

    stages {
        stage('Build') {         
            steps {
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
