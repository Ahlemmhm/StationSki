pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3' // This should match the name you configured in Global Tool Configuration
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
