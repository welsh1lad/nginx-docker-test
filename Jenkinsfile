pipeline {
    agent any {
 
    stage 'Check-repo'
        sh "git clone https://github.com/welsh1lad/nginx-docker-test.git"
    
    stage 'Build'
        sh "docker build -t nginx:latest -f Dockerfile ."
        
  
    stage 'Run'
    sh "docker run -d -p8090:80 nginx:latest"
     
    stage 'Test'
     sh "curl -s http://localhost:8090 | grep Welcome | head -n1" 
     
}
}
