pipeline {
          
          agent any

             stages { 
                 stage('github') {
                     steps { 
                       
                            git branch: 'main', credentialsId: 'git-jenkins-node', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                         
                          }  

                  }   
                 

      }          





}
