 pipeline
{

agent any
tools{
maven 'maven3'
jdk 'jdk8'
}
stages {
  stage ('Build') {
 
 steps     {
 
      sh "mvn clean install"
 
    } 
  }
        stage('Test') {
            steps {
                sh 'make check'
            }
    post {
        always {
            junit '\Users\YESHU\Desktop\junit.xml'
        }
      }
   }
 }
}
