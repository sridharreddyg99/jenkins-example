node('master'){
stage 'checkout'
 { checkout scm
  }
stage 'build'{
  withEnv(["JAVA_HOME=${ tool 'jdk8' }", "PATH+MAVEN=${tool 'maven3'}/bin:${env.JAVA_HOME}/bin"]) {
  sh "mvn clean verify"}
}
}
