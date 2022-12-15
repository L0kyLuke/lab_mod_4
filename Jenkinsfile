pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
    url: 'https://github.com/L0kyLuke/lab_mod_4.git'
            }
        }
        stage('Compile') {
            steps {
                sh './gradlew.bat compileJava'
            }
        }
        stage('Unit Tests') {
            steps {
                sh './gradlew.bat test'
            }
        }
    }
}