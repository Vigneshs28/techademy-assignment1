pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'mvn clean'
      }
    }
    stage('Test') {
      steps {
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn package'
      }
    }
  }
  post {
    always {
        emailext body: 'Current Build Failed. Please Review It.', to: 'vigneshsubramani28@gmail.com,dondom828@gmail.com' , subject: 'Build Failed'
    }
  }
}
