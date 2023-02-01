    pipeline {
        agent any

        stages {
            stage('Checkout') {
                steps {
                    git url: 'https://github.com/L0kyLuke/lab_mod_4.git', branch: 'main'
                }
            }
            stage('Compile') {
                steps {
                    sh './calculator/gradlew compileJava'
                }
            }
            stage('Unit Tests') {
                steps {
                    sh './calculator/gradlew test'
                }
            }
        }
    }