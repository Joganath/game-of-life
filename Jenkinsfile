@Template_01

node('Linux_Agent'){
  stage('code_checkout')
  {
   Code_Checkout()
  }
  stage('Cleanup directory')
  {
  Cleanup(${WORKSPACE})
  }
  stage('build')
  {
  Build()
  }
  
  }  