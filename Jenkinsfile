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
			       def server =Artifactory.server 'Artifactory_Server_01'
				   def uploadspec = """{
				   
				                        "files": [
										    {
											  "target" : "libs-release-local/${BUILD_NUMBER}"
											  "pattern": "target\\*.war"
											}
                                                 ]
                                        }"""
                    server.upload(uploadspec)
					 }
                    					
			         echo "Artifact succesfully Uploaded to Artifactory Further Verification in artifactory required"
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


       





