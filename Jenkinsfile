stage 'checkout'
node ('master'){
    checkout scm
}

stage 'build'
node ('master'){

     
   withEnv(["JAVA_HOME=${ tool 'jdk8' }", "PATH+MAVEN=${tool 'maven3'}/bin:${env.JAVA_HOME}/bin"]) {

   
    sh "mvn clean verify"
 }
}
stage 'test'
node('master'){
   steps {
                /* `make check` returns non-zero on test failures,
                * using `true` to allow the Pipeline to continue nonetheless
                */
                sh 'make check || true' 
                junit '**/target/*.xml'
   }
}   
