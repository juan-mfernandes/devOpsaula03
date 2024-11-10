pipeline {
    agent any
    stages {
		stage('Iniciando ambiente Python') {
			steps {
				sh 'python3 -m venv venv'
				sh 'source venv/bin/activate'
			}
		}
        stage('Build') {
            steps {
                echo 'Instalando dependências...'
				sh 'pip -r install requirements.txt'
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
