pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                docker run -d -p8080:80 nginx:v2
                
            }
        }
    }
}
