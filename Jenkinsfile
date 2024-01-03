pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                echo 'Hello build'
            }
        }
        stage('test') {
            steps {
                echo 'Hello test'
            }
        }
        stage('deploy') {
            steps {
                echo 'Hello deploy'
            }
        }
    }

// post is used to write code for post build actions we can use "always" , "failure", "success", "unstable", "changed"

    post {
        always {

// echo is used to print the statement

 echo 'Running the test !'
          emailext body: 'Plz find the results', subject: 'Test results', to: 'sanjaykumar.marolix@gmail.com'  
        }
    }
}
