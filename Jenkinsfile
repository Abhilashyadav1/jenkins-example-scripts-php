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
                sh """-D sonar.login=admin \
        -D sonar.password=admin123 \
        -D sonar.projectBaseDir=/var/lib/jenkins/workspace/test/ \
        -D sonar.projectKey=1afc8b67667a560831b2b764f5891b0d75eedb4d\
        -D sonar.sourceEncoding=UTF-8 \
        -D sonar.language=java \
        -D sonar.host.url=http://184.72.166.153:9000/"""
                }
            }
        }
    }
}
