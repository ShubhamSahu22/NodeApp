pipeline {

         agent any 
            
               stages {
                   stage('github'){
                     steps {
                           git branch: 'main', credentialsId: 'git-docker-node ', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                      } 

                  }    
             
           }


}
