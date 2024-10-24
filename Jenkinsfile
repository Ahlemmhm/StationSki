pipeline {
    agent any
    tools {
        maven 'M2_HOME' // This should match the name you configured in Global Tool Configuration
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
