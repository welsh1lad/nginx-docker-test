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
        sh 'docker build --label dev -t nginx/my-www:latest .'
          }
        }
        stage('Docker Run Build') {
            steps {
                sh 'docker run -d --publish 8090:80 --detach --name my-www1 nginx/my-www:latest'
            }
        }
        Stage('Health Check') {
            steps {
                def testResult =  'curl -vv http://localhost:8090'
                if (testResult == 'Failed') {
                          error "test failed"
                          }
                  }
          }
          
        Stage('Clean Up') {
            steps {
                sh 'docker stop my-ww1'
                sh 'docker rmi -f nginx/my-www:latest'
            }
        }  
              
    }
}
