pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Instalando dependências...'
				sh 'pip -r install requirements.txt
			}
		}
		stage('Iniciando ambiente Python') {
			steps {
				sh 'pip -m venv venv'
				sh 'source venv/bin/activate'
			}
		}
        stage('Deploy') {
            steps {
                echo 'Executando aplicação...'
				sh 'python main.py'
            }
        }
    }
}
