pipeline {
          agent any
          tools {
          nodejs 'NodeJS'
          } 




                 stages {

                    stage('github') {
                             steps { 
                               git branch: 'main', credentialsId: 'docker-jenkine-token-ken', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                            }
                       }      
                       stage('Unit Test') {  
                        steps { 
                            sh 'npm test'
                            sh 'npm install'
                          
                        
                         }
                      
                     
                   }

               }



}








