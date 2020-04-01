pipeline { 
   agent any
   //  options {
   //     skipStagesAfterUnstable()
   // }
   stages {
        
      stage('Pre-Clean Up') {
      agent any
      steps {
          
        sh 'docker stop my-ww1 | echo "Ignore Error if container is not running"'
        sh 'docker rm my-www1 | echo "Ignore Error if contain is not found"'
        sh 'docker rmi nginx/my-www:latest | echo "Ignore Error if Image is not there"' 
        sh 'rm -rf /var/lib/jenkins/workspace/nginx-www_master/nginx-docker-test | echo "ignore"' 
        sh ' rm -rf /root/nginx-docker-test | echo " Ignore error"'
        
           }
        }  
        
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
        sh 'docker stop my-ww1 | echo "Ignore Error if container is not running"'
        sh 'docker rm my-www1 | echo "Ignore Error if contain is not found"'
        sh 'docker rmi nginx/my-www:latest | echo "Ignore Error if Image is not there"'   
        sh 'docker rmi -f var/lib/jenkins/workspace/nginx-www_master/nginx-docker-test'
            }
        }  
   }
}
