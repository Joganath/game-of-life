@Library('Template_01') _

node('Linux_Agent')
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