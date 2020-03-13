pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                docker -t nginx-test:v0.0.1 build .
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
