pipeline {
    agent {
        docker {
            image 'jenkins-agent:latest'
            args ' -p32121:32121 -p2376:2376 -p4243:4243 -p8090:8090 --privileged' 
        }
    }   
    
    stages {
        stage('Build') {
            steps {
                sh 'echo "Now building"'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Now Testing"'
            }
        }
}
}    
