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
        stage('SonarQube') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''sonar-scanner \\
  -Dsonar.projectKey=sample \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://184.72.166.153:9000 \\
  -Dsonar.login=sonar
'''
                }
            }
        }
    }
}
