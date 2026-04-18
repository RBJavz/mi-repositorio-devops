pipeline {
    agent any

    environment {
        VM_IP = "192.168.1.11"
        VM_USER = "javz"
    }

    stages {
        stage('Deploy en VM') {
            steps {
                bat """
                ssh -o StrictHostKeyChecking=no -o ConnectTimeout=10 %VM_USER%@%VM_IP% ^
                "cd mi-repositorio-devops || git clone https://github.com/RBJavz/mi-repositorio-devops.git && ^
                cd mi-repositorio-devops && ^
                docker-compose up -d --build"
                """
            }
        }
    }
}
