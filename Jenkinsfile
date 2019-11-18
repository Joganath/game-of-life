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
		          bat 'set Source = C://Jenkins//workspace//Game_Of_Life_MBP1_Feature1//gameoflife-web//target//gameoflife.war'
				  bat 'set Dest = C://Program Files//Apache Software Foundation//Tomcat 9.0//webapps'  
				  bat 'xcopy /s Source Dest'
				  bat 'start cmd.exe /c  C://Program Files//Apache Software Foundation//Tomcat 9.0//bin//startup.bat'
				   echo "deployment done pls Verify if corectly deployed"				}  
		   
		     
         }		 
		  
		}

        }


       





