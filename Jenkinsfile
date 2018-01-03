node {
  git url: 'https://github.com/yeshwanth1312/jenkins-example/blob/master/Jenkinsfile.git'
   withEnv(["JAVA_HOME=${ tool 'jdk8' }", "PATH+MAVEN=${tool 'maven3'}/bin:${env.JAVA_HOME}/bin"]) {
    sh 'mvn -B verify'
  }
}

