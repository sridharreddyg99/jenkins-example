stage 'checkout'

node ('master'){

    checkout scm


stage 'build'

node ('master'){
   withEnv(["JAVA_HOME=${ tool 'jdk8' }", "PATH+MAVEN=${tool 'maven3'}/bin:${env.JAVA_HOME}/bin"]) {
    sh "mvn clean verify"

 }

}


        stage 'Reports'
node('master'){

                allure results: [[path: 'target/allure-results']]

            }
stage 'Test'

node('master'){
            
                sh 'make check || true' 
                junit '**/target/*.xml'
}
}
