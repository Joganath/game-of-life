pipeline {

  agent {
          label 'Linux_Agent'
		  
		 } 
  options{
           timeout(time: 30,unit: 'HOURS')
  
         }
  stages{   
    stage('Build') 
         {
           when {
                 branch 'master'
                 }
           steps {
                   sh 'mvn clean install'
                 }
          }
          
	/*stage('Upload')
          {
		   steps{
               script{
			       def server = Artifactory.server('Artifactory_Server_01')
				   def uploadSpec = """{
				   
				                        "files": [
										    {
											  "pattern": "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-web\\target\\(*).war",
											  "target" : "libs-snapshot-local/${BUILD_NUMBER}/"
											  },
											  
											 {
                                              "pattern": "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-build\\target\\(*).jar",
											  "target" : "libs-snapshot-local/${BUILD_NUMBER}/"
											 
											 },
											 {
											  "pattern": "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-core\\target\\(*).jar",
											  "target" : "libs-snapshot-local/${BUILD_NUMBER}/"
											 
											 }
											 
                                                 ]
                                        }"""
                    server.upload(uploadSpec)
					def buildInfo = server.upload(uploadSpec)
					server.publishBuildInfo(buildInfo)
					 }
                    					
			         echo "Artifact/Artifacts successfully Uploaded to Artifactory,However Further Verification in artifactory required for confirmation"
			    }

          }     
	
	 stage('Deploy')
         {
           steps{
		         bat 'xcopy /S "C:\\Jenkins\\workspace\\Game_Of_Life_MBP1_Feature1\\gameoflife-web\\target\\gameoflife.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"'
				  bat 'start cmd.exe /c  C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\bin\\startup.bat'
				   echo "deployment done please Verify if correctly deployed or not"
				}  
		   
		     
         }*/	 
	     }        
		
	   post{
            failure{
			       mail to : 'joganath.sahoo@gmail.com',
                   subject : 'GOI_Build Failed', body : 'PLease fix and rerun'
                   }
            success{
                    mail to : 'joganath.sahoo@gmail.com',
                    subject : 'GOI_Build${BUILD_NUMBER}', body : 'Build Done'
					}
			}		
                 					
			
        	   
		
    }


       





