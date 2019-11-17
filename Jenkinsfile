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
          
	stage('Deploy')
         {
           steps{
		          bat 'xcopy /s C:\Jenkins\workspace\Game_Of_Life_MBP1_Feature1\gameoflife-web\target C:\Program Files\Apache Software Foundation\Tomcat 9.0\webapps'
				  bat 'C:\Program Files\Apache Software Foundation\Tomcat 9.0\bin\startup.bat'
				}  
		   
		     
         }		 
		  
		}

        }


       





