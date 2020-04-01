pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('build') { 
            steps { 
                
                sh 'git clone https://github.com/welsh1lad/nginx-docker-test.git'
            }
        }
      stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t nginx/my-www:latest .'
          }
        }
        stage('Deploy') {
            steps {
                sh 'echo ... deploy ...'
            }
        }
    }
}
