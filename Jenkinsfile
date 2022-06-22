pipeline {
    agent any
    options {
                ansiColor('xterm')
                timestamps ()
                disableConcurrentBuilds()
                buildDiscarder(logRotator(numToKeepStr: '5'))
    }

    stages {
        stage('Gradle sonarqube') {
            steps {
                withSonarQubeEnv('My SonarQube Server', envOnly: true) {
                    sh './gradlew sonarqube'
                }
            }
        }
    }
}