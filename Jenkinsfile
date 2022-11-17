pipeline {
  agent any
  stages {
    stage('install') {
      steps {
        sh 'php --version'
      }
    }
    stage('hello') {
      steps {
        sh 'php hello.php'
      }
    }
    stage('codequality') {
      steps {
        withSonarQubeEnv('SonarQube') {
          sh 'mvn clean package sonar:sonar'
        }  
      }
    }
  }
}
