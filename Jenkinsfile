pipeline {
    agent { docker { image 'maven:3.3.3' } }
    environment {
      GREETING = 'Hello world!'
      OTHER = 'Other env var'
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh "echo $GREETING"
                sh 'printenv'
            }
        }
        stage('confirm') {
          steps {
            input 'Continue?'
          }
        }
        stage('complete') {
          steps {
            sh 'echo "confirmed!"'
          }
        }
    }
    post {
      always {
        echo 'Build completed'
      }
      success {
        echo 'Build successful!'
      }
      failure {
        echo 'Build failed :('
      }
    }
}