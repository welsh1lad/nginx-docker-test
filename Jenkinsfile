
       node { 
             label 'docker'
              
             checkout scm 
             sh 'git clone https://github.com/welsh1lad/nginx-docker-test.git'
             sh 'cd  nginx-docker-test'
             docker.build "my-www:latest" 
             docker.image('nginx/my-www:latest').withRun('-e --name my-www1 -d --publish 8090:80 --detach') { c ->
             sh 'echo " Run a Test on the nginx container"'
             sh 'curl http://localhost:8090'
          }
       }

