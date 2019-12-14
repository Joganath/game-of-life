pipeline {

  agent none
  
  stages{   
    stage('Build') 
         {
           when {
                 branch 'Feature1'
                 }
           steps {
                   sh 'mvn clean install'
                 }
          }
          
	stage('Upload')
          {
		   steps{
               script{
			       def server =Artifactory.server('Artifactory_Server_01')
				   def uploadSpec = """{
				   
				                        "files": [
										    {
											  "pattern": "**\\target\\*.war"
											  "target" : "libs-release-local/${BUILD_NUMBER}"
											  
											}
                                                 ]
                                        }"""
                    server.upload(uploadSpec)
					 }
                    					
			         echo "Artifact/Artifacts succesfully Uploaded to Artifactory, Further Verification in artifactory required for confirmation"
			    }

          }     
	
	 stage('Deploy')
         {
           steps{
		         bat 'xcopy /S "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-web\\target\\gameoflife.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"'
				  bat 'start cmd.exe /c  C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\bin\\startup.bat'
				   echo "deployment done please Verify if correctly deployed or not"
				}  
		   
		     
         }		 
	             
		}

        }


       





