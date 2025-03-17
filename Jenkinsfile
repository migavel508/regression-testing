pipeline {
    agent any

    tools {
        maven 'Maven' // Ensure Maven is installed in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/migavel508/regression-testing.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/TEST-*.xml'

        }
    }
}
