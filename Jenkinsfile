stage 'checkout'

node ('master'){

    checkout scm


stage 'build'


   withEnv(["JAVA_HOME=${ tool 'jdk8' }", "PATH+MAVEN=${tool 'maven3'}/bin:${env.JAVA_HOME}/bin"]) {
    sh "mvn clean verify"

 }



        stage 'Reports'


                allure results: [[path: 'target/allure-results']]

            
stage 'Test'


            
                sh 'make check || true' 
                junit 'FizzBuzzTest.java'
}
