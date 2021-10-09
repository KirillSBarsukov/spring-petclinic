pipeline {
    agent { label 'linux' }
    tools { 
        maven 'maven-3.8.3'
    }
    stages {
        stage('checkot') {
            steps {
                git "https://github.com/KirillSBarsukov/spring-petclinic.git"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clear compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
