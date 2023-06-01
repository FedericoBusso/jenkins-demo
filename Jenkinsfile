pipeline {
    agent any

    stages {
        stage('Build') {         
            steps {
                sayName 'Mark'
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
