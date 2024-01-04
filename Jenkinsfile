pipeline {
    agent any
    tools {
        maven "apache-maven-3.9.6"
        jdk "jdk-11"
    }
    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${MAVEN_HOME}/bin:${PATH}"
                echo "MAVEN_HOME = /opt/maven"
            }
        }
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/demopipelinetask/my-app") {
                sh 'mvn -B -DskipTests clean package'
                }
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}
