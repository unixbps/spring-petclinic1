pipeline {
    agent { label 'master' }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/unixbps/spring-petclinic1.git'
          }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
