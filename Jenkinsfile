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
                sh '''
                    # Crear entorno virtual
                    python3 -m venv venv
                    # Activar entorno
                    . venv/bin/activate
                    # Actualizar pip y dependencias
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    # Ejecutar bandit desde el entorno
                    bandit -r . || true
                '''
            }
        }
    }
}