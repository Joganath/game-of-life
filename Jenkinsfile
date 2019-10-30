pipeline {

agent {

label 'Windows10_Agent'
}

stage('Build') {
when {
allOf{branch 'Feature1';triggeredBy 'SCMTrigger'}
steps {
mvn 'clean install'
}

}

}


}





