pipeline {
          agent any
          
          tools {
               nodejs 'NodeJS'
       }
      environment {
            SONAR_PROJECT_KEY= 'NodeApp-Token'
            SONAR_SCANNER_HOME= 'SonarQubeScanner"

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
             stage("SonarQube") { 
                     steps{ 
                         withCredentials([string(credentialsId: 'NodeApp-Token', variable: 'SONAR_TOKEN')]) { 
                                       
                                                 withSonarQubeEnv('SonarQube') {
                                                            sh """
                                                            ${SONAR_SCANNER_HOME}/bin/sonar-scanner \
                                                            -Dsonar.projectKey=${SONAR_PROJECT_KEY} \
                                                            -Dsonar.sources=. \
                                                            -Dsonar.host.url=http://44.201.206.149:9000 \
                                                            -Dsonar.login=${SONAR_TOKEN} 
                                                            """  
                                                  }
                                          
                                       
                                     }
                                      

                             } 
                  
                  }
          }

}
