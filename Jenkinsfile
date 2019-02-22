pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'echo "Hello world!"'
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