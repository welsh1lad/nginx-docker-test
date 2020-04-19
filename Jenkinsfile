node { 
             label 'docker'
              
             checkout scm 
             docker.image('jenkins-agent:latest').inside("-e COMPOSER_HOME=/tmp/jenkins-workspace") {
               sh 'hostname'
               }
     }          
