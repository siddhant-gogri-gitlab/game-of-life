pipeline {
    agent any 
    tools {
      maven 'apache-maven-3.3.1'
    }
    stages {
        stage('Build and Test') {
            steps {
                sh 'mvn clean package'
                sh 'echo "build ran"'
                archiveArtifacts artifacts: 'gameoflife-web/target/gameoflife.war', fingerprint:true
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}
