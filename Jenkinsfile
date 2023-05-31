pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker { image 'node:16' }
            }
            steps {
                sayHello "Mark"
                echo 'Building..'
            }
        }
        stage('Test') {
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
