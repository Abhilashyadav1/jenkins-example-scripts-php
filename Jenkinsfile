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
                    sh '''/root/sonarqube-8.9.10.61524/bin/linux-x86-64/sonar-scanner-4.7.0.2747-linux/bin/./sonar-scanner
sonar-scanner \\
  -Dsonar.projectKey=sample \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://184.72.166.153:9000 \\
  -Dsonar.login=admin'''
                }
            }
        }
    }
}
