pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "This is the build number $BUILD_NUMBER"
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