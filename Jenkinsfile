pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Construyendo el proyecto...'
            }
        }
        stage('Test') {
            steps {
                echo 'Ejecutando pruebas...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Instalando herramientas de seguridad...'
                sh 'pip install -r requirements.txt --break-system-packages'
                echo 'Ejecutando análisis estático con Bandit...'
                sh 'bandit -r . || true'
            }
        }
    }
}