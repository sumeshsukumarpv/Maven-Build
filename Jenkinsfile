pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat10(credentialsId: 'tomcat-cred', path: '', url: 'http://http://43.205.118.132:9090')], contextPath: '/', war: '**/*.war'
            }
        }
    }
}
