pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: https://github.com/L0kyLuke/lab_mod_4.git
            }
        }
        stage('Compile') {
            steps {
                sh './gradlew compileJava'
            }
        }
        stage('Unit Tests') {
            steps {
                sh './gradlew test'
            }
        }
    }
}