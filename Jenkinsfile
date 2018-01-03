node {
  git url: 'https://github.com/yeshwanth1312/jenkins-example/edit/master/Jenkinsfile.git'
  withEnv(["PATH+MAVEN=${tool 'maven3'}/bin"]) {
    sh 'mvn -B verify'
  }
}
