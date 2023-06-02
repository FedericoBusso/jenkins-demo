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
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
