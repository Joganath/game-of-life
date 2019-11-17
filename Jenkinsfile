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
		          bat 'xcopy "C://Jenkins//workspace//Game_Of_Life_MBP1_Feature1//gameoflife-web//target//gameoflife.war" "C://Program Files//Apache Software Foundation//Tomcat 9.0//webapps"'
				  bat 'call C://Program Files//Apache Software Foundation//Tomcat 9.0//bin//startup'
				  bat 'echo "deployment done"'
				}  
		   
		     
         }		 
		  
		}

        }


       





