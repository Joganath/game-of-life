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
          
	stage('Upload')
          {
		   steps{
               script{
			       def server = Artifactory.server('Artifactory_Server_01')
				   def uploadSpec = """{
				   
				                        "files": [
										    {
											  "pattern": "Game_Of_Life_MBP1_Feature1\\gameoflife-web\\target\\*.war",
											  "target" : "libs-snapshot-local/GOIBuild1"
											  }
                                                 ]
                                        }"""
                    server.upload(uploadSpec)
					def buildInfo = server.upload(uploadSpec)
					server.publishBuildInfo(buildInfo)
					 }
                    					
			         echo "Artifact/Artifacts succesfully Uploaded to Artifactory,However Further Verification in artifactory required for confirmation"
			    }

          }     
	
	 /*stage('Deploy')
         {
           steps{
		         bat 'xcopy /S "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-web\\target\\gameoflife.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"'
				  bat 'start cmd.exe /c  C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\bin\\startup.bat'
				   echo "deployment done please Verify if correctly deployed or not"
				}  
		   
		     
         }*/	 
	             
		}

        }


       





