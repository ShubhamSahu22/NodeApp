pipeline {
          
          agent any
           tools {

              nodejs 'NodeJS'
        }


             stages { 
                 stage('github') {
                     steps { 
                       
                            git branch: 'main', credentialsId: 'git-jenkins-node', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                         
                          }  

                  }   
                 
                  stage('install  node dependency') {

                    steps { 
                         sh 'npm install'
                                 

                   }    

            }

                   stage('Test case') {

                          steps  { 

                                 sh 'npm test'

                   }

             }




      }          





}
