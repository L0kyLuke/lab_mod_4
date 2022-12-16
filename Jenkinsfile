pipeline {
    agent {
        docker { image 'java-docker-slave' }
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/L0kyLuke/lab_mod_4.git', branch: 'main'
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