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
	stage('MVN Sonarqube') {
            steps {
                sh "mvn sonar:sonar -Dsonar.login=squ_72d245dc80fbe69602edd4bc4e4c6cad3c0bff6e"
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
