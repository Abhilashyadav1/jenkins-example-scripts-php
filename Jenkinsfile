pipeline {
  agent any
  stages {
    stage('install') {
      steps {
        sh 'install php latest'
      }
    }
    stage('hello') {
      steps {
        sh 'php hello.php'
      }
    }
  }
}
