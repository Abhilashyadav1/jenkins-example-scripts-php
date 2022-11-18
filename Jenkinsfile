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
                sh """sonar.login=admin \
        sonar.password=admin123 \
        sonar.projectBaseDir=/var/lib/jenkins/workspace/test/ \
        sonar.projectKey=1afc8b67667a560831b2b764f5891b0d75eedb4d\
        sonar.sourceEncoding=UTF-8 \
        sonar.language=java \
        sonar.host.url=http://184.72.166.153:9000/"""
                }
            }
        }
    }
}
