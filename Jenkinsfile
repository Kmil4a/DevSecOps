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
                    . venv/bin/activate
                    # Actualizar pip y dependencias
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    # Instalar pbr (dependencia requerida por Bandit)
                    pip install pbr
                    # Ejecutar Bandit
                    bandit -r . || true
                '''
            }
        }
    }
}

