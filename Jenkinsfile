pipeline {
  agent any
  tools {
    maven 'Local Maven'
  }
  stages {
    stage('checkout') {
      steps {
        git branch: '${env.BRANCH_NAME}', credentialsId: 'athulk918', url: 'https://github.com/athulk918/multimaven.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
    
  }
}
