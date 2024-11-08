pipeline {
  /*
   * TODO: Implement pipeline stages/steps
   *   See documentation: https://www.jenkins.io/doc/book/pipeline/syntax/#stages
   */

   agent any

   environment {
            GRADLE_HOME = '/opt/gradle' 
   }
  stages{
    stage('Checkout') {
            steps {
                checkout scm
            }
        }

   stage('Build'){
    steps {
      echo 'Building the application'
      script {
        sh './gradlew assemble'
      }
    }

   }

   stage('Test'){
    steps {
      echo 'Testing the application'
      script {
        sh './gradlew test'
      }
    }

   }
  }

  post{
    success{
                  echo 'Build and tests completed successfully.'
    }
    failure {
            echo 'Build or tests failed.'
        }
  }
}
