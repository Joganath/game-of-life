@Library('LibRepo01@master')
import jenkins.sharedlib.*
def lib01 = new Shared_Lib01()	

node('Linux_Agent')
{
  stage('code_checkout')
  {
    lib01.Code_Checkout()
  }
  stage('Cleanup directory')
  {
    lib01.Cleanup(${WORKSPACE})
  }
  stage('build')
  {
    lib01.Build()
  }
  
}  