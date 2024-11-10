pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Instalando dependências...'
				sh 'pip install -r requirements.txt'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Executando aplicação...'
				sh 'python app.py'
            }
        }
    }
}
