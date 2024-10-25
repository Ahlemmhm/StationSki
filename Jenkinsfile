pipeline {
    agent any

    tools {
        maven 'M2_HOME'
    }

    stages {
        stage('Clean') {
            steps {
                script {
                    sh 'mvn clean'
                }
            }
        }

        stage('Compile') {
            steps {
                script {
                    sh 'mvn compile -DskipTests'
                }
            }
        }

        stage('Sonar-Test') {
            steps {
                script {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'mvn test -DskipCompile'
                }
            }
        }

        stage('Package') {
            steps {
                script {
                    sh 'mvn package -DskipTests -DskipCompile'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
        success {
            echo 'Build was successful!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
