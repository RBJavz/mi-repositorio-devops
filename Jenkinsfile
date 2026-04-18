pipeline {
    agent any

    stages {

        stage('Clonar repositorio') {
            steps {
                git 'https://github.com/RBJavz/mi-repositorio-devops.git'
            }
        }

        stage('Construir Docker') {
            steps {
                sh 'docker build -t mi-app ./app'
            }
        }

        stage('Ejecutar contenedor') {
            steps {
                sh 'docker run -d -p 5000:5000 mi-app'
            }
        }

    }
}
