
       node { 
             label 'docker'
              
             checkout scm 
             docker.image('jenkins-agent:latest').inside("-e COMPOSER_HOME=/tmp/jenkins-workspace") {
               sh 'hostname'
               docker.build "my-www:latest" 
               docker.image('nginx/my-www:latest').withRun('-e --name my-www1 -d --publish 8090:80 --detach') { c ->
               sh 'echo " Run a Test on the nginx container"'
               sh 'curl http://localhost:8090'
          }
       }
       }
