pipeline { 
   agent { node { label 'docker' }} 
   //  options {
   //     skipStagesAfterUnstable()
   // }
   stages {
       
    docker.image('nginx/my-www:latest').withRun('-e --name my-www1 -d --publish 8090:80 --detach') { c ->
        sh 'echo " Run a Test on the nginx container"'
        sh 'curl http://localhost:8090'
      
    }
}  
}        
      // stage('Clone') {
           
      // steps {  
      //        sh 'git clone https://github.com/welsh1lad/nginx-docker-test.git'
      //        }
      // }

     
       
      //stage('Docker Run Build') {
     
      //steps {
       
      //  sh 'docker run -d --publish 8090:80 --detach --name my-www1 nginx/my-www:latest'
      //      }
      //  }
        
      //stage('Test Running Container') {
      //   steps{
      //      sh 'curl http://localhost:8090'
      //      }
      //}
            

 //  }
//}
