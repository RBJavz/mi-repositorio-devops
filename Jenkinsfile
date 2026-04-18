pipeline {
    agent any

    environment {
        VM_IP = "192.168.1.11"
        VM_USER = "javz"
    }

        stage('Deploy en VM') {
            steps {
                sh """
                ssh ${VM_USER}@${VM_IP} '
                cd mi-repositorio-devops || git clone https://github.com/RBJavz/mi-repositorio-devops.git
                cd mi-repositorio-devops
                docker stop mi-contenedor || true
                docker rm mi-contenedor || true
                docker-compose up -d --build
                '
                """
            }
        }
    }
}
