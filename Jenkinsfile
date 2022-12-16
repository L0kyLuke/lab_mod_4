pipeline {
    agent {// especificamos que el agente será Docker. Al estar en la raíz todos los stages se ejecutarán en un contenedor que use la imagen de Docker, así si trabajamos con distintos nodos no hace falta instalar Node.js en cada uno de ellos
        docker {
            image 'jenkins/jenkins:lts' // Especificamos la imagen a utilizar que se instalará en el nodo de Docker y se accederá desde el nodo de Jenkins
        }
    }
    stages {
        stage('Verify') {
            steps {
                sh '''
                  node --version
                  npm version
                '''
                sh 'printenv | sort' // Imprimir variables de intorno
            }
        }
        stage('Build') { // Hacemos el build del proyecto solution usado anteriormente
            steps {
                dir("$WORKSPACE/02/solution") { // Ponemos la ruta donde tenemos el proyecto deejemplos anteriores copiado
                    sh '''
                      npm install
                      npm run build
                    '''
                }
            }
        }
        stage('Unit Test') { // Hacemos un test
            steps {
              dir("$WORKSPACE/02/solution") {
                sh 'npm test'
              }
            }
        }
    }
}