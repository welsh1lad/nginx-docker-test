
       node { 
             label 'docker'
              stages {
                     stage ('start docker service in container')
                     {
                            steps{
                                   sh 'service docker start'
                            }
                     }}
              
             checkout scm 
             docker.image('nginx/my-www:latest').withRun('-e --name my-www1 -d --publish 8090:80 --detach') { c ->
             sh 'echo " Run a Test on the nginx container"'
             sh 'curl http://localhost:8090'
          }
       }
