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
                    sh '/root/sonarqube-8.9.10.61524/bin/linux-x86-64/.sonar.sh start'
                }
            }
        }
    }
}
