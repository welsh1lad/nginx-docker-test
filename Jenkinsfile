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
      agent any
      steps {
        sh 'docker run -d --publish 8090:80 --detach --name my-www1 nginx/my-www:latest'
            }
        }
        
          
      stage('Clean Up') {
      agent any
      steps {
        sh 'docker stop my-ww1'
        sh 'docker rmi -f nginx/my-www:latest'
            }
        }  
              
    }
}
