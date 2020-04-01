pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'C:\\apache-maven-3.6.3\\bin\\mvn clean'
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
        emailext body: 'Current Build Failed. Please Review It.', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'DefaultRecipientProvider']], subject: 'Test'
    }
  }
}
