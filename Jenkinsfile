node('Linux_Agent'){
  stage('Print_Env_Vars')
  {
  if (env.BRANCH_NAME=='Feature1')
  {
  sh 'mkdir /var/lib/jenkins/${BRANCH_NAME}'
  println'Some Environment variables printed pls check'
  }
  
  }
  }  