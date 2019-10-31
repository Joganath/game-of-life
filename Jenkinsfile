pipeline {

  agent {
     label 'Windows10_Agent'
        }
  stages{   
    stage('Build') 
         {
           when {
                 branch 'Feature1'
                 }
           steps {
                   bat 'mvn clean install'
                 }
          }
          }

        }


       





