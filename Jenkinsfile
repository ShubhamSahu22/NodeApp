pipeline {

         agent any 
         tools {
              nodejs 'NodeJS'
         }

            
               stages {
                   stage('github'){
                     steps {
                           git branch: 'main', credentialsId: 'git-docker-node ', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                      } 

                  }
                   stage('install node dependency') {
                         steps {
                               sh 'npm install'
                          }                
                           
                       }    
                       stage('Test case'){
                         steps { 

                               sh 'npm test'
                         }
                 
                    } 
                    stage('Build Docker Images') {
                         steps {
                                 sh 'docker.build("nodeimage"+"$BUILD_NUMBER")'
                        } 
                 }          

  
           }

           post {
                   success { 
                           echo 'Build completed succesfully!'
                             
                  }
                  failure {
                          echo 'Build failed. check logs.'

                 }  
          
          } 
            
}
