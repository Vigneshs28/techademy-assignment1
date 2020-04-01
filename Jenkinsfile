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
        emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
    }
  }
}
