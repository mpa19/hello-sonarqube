pipeline {
    agent any
    options {
                ansiColor('xterm')
                timestamps ()
                disableConcurrentBuilds()
                buildDiscarder(logRotator(numToKeepStr: '5'))
    }

    stages {
        /*stage('Gradle sonarqube') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh './gradlew sonarqube'
                }
            }
        }*/

        stage('Publish gradle nexus') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'nexus1', passwordVariable: 'TOKEN', usernameVariable: 'USERNAME')]) {
                    withGradle {
                        sh './gradlew publish'
                    }
                }
            }
        }
    }
}