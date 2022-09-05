pipeline {
   environment {
    registry = 'dockerhub0126/test1'
    registryCredential = 'docker-id'
    dockerImage = ' '
            }
     agent any
     tools {
           maven 'mvn-3.8.6'
           }
      stages{
          stage("VERSION")
            {
             steps {
                sh " mvn --version"
                    }      
              }
              
       stage("Clean and Package")
       {
         steps {
               sh "mvn clean package"
                 }
               }
               
          stage("DEPLOY")
          {
            steps{
                  echo "Deploy code goes here"
                  sh "docker build --tag=webapp-hello ."
                  sh "docker tag webapp-hello dockerhub0126/test1:webapp-v1-290822"
                  sh "docker push dockerhub0126/test1:webapp-v1-290822"
                  }
                }
               }
              }