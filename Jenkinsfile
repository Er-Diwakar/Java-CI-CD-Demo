pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t java-ci-app:1.0 .'
            }
        }

        stage('Run Application') {
            steps {
                sh 'docker run --rm java-ci-app:1.0'
            }
        }
    }
}
