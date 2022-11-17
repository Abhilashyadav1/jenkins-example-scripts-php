pipeline {
  agent any
  stages {
    stage('install') {
      steps {
        sh 'install php'
      }
    }
    stage('hello') {
      steps {
        sh 'php hello.php'
      }
    }
  }
}
