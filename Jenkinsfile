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
                    sh" ${SCANNER_HOME}}/bin/sonar-scanner \
                    -Dsonar.projectKey=simple_webapp \
                    -Dsonar.sources=. "   
                }
            }
        }
    }
}
