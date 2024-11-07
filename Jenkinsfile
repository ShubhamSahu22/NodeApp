pipeline {
          agent any
          tools {
          nodejs 'NodeJS'
          } 
          environment {
                SONAR_PROJECT_KEY=  'NodeApp-ecs'
                SONAR_SCANNER_HOME= tool 'SonarQubeScanner'
           
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
                   stages { 
                        stage('SonarQube Analysis') { 
                 
                         steps { 
                             
                              withCredentials([string(credentialsId: 'NodeApp-ecs-token', variable: 'SONAR_TOKEN')]) {
    
                                    
                                                withSonarQubeEnv('SonarQube') {
                                                          
                                                sh """
                                                ${SONAR_SCANNER_HOME}/bin/sonar-scanner \
                                                -Dsonar.projectKey=${SONAR_PROJECT_KEY} \
                                                -Dsonar.sources=. \
                                                -Dsonar.host.url=http://18.233.101.139:9000 \
                                                -Dsonar.login=${SONAR_TOKEN}
                                                """
                                                }      

                                      }      


                              }              

                         }

                 } 
       

       }

}








