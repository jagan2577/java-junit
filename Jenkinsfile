pipeline {
    agent any
    tools{
        nodejs '18.9.1'
    }

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/jagan2577/java-junit.git'
                // sh './mvnw clean compile'
                 bat '.\\mvnw clean compile'
                   npm version
            }
        }
        stage('Test') {
            steps {
                // sh './mvnw test'
                bat '.\\mvnw test'
            }

            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }
    }
}
