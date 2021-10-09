pipeline {
    agent { label 'linux' }
    tools { 
        maven 'maven-3.8.3'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: "https://github.com/KirillSBarsukov/spring-petclinic.git"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
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
