@Library('Template_01')

node('Agent_01_Centos8')
{
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