pipeline {
    agent any
    stages {
        stage("Maven build") {
            steps {
                bat 'mvn -B clean package'
            }
        }
        stage("Gatling run") {
            steps {
                bat 'mvn gatling:test'
            }
            post {
                always {
                    gatlingArchive()
                }
            }
        }
    }
}