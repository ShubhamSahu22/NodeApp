pipeline {
          agent any
          
          tools {
               nodejs 'NodeJS'
    }
            stages {
                stage("github") { 
                  steps { 
                          git branch: 'main', credentialsId: 'jenkins-token-key', url: 'https://github.com/ShubhamSahu22/NodeApp.git'
                       }
   
                 }

                stage("NodeJS Dependency") {
                 steps { 
                          sh 'npm install'
                        }
               }
              stage("npm test") { 
                 steps { 
                     sh 'npm test'
                   }
                }
       }

}
