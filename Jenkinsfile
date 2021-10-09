pipeline {
    agent { docker 'maven:3.8.3-jdk-11' }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: "https://github.com/KirillSBarsukov/spring-petclinic.git"
            }
        }
        stage('Build') {
            steps {
                    sh 'mvn --version'
                 sh 'mvn clean package'
                 junit '**/target/surefire-reports/TEST-*.xml'
                 archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
