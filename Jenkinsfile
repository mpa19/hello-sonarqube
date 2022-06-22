pipeline {
    agent any
    options {
                ansiColor('xterm')
                timestamps ()
                disableConcurrentBuilds()
                buildDiscarder(logRotator(numToKeepStr: '5'))
    }

    stages {
        stage('Init docker sonarqube') {
            steps {
                sh 'docker-compose up'
            }
        }

        stage('Gradle sonarqube') {
            steps {
                sh './gradlew sonarqube'
            }
        }
    }
}