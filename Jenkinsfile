pipeline {
    agent any
    stages {
		stage('Iniciando ambiente Python') {
			steps {
				sh 'python -m venv venv'
			}
		}
        stage('Build') {
            steps {
                echo 'Instalando dependências...'
				sh '''
					source venv/bin/activate
					pip install -r requirements.txt'
				'''
			}
		}	
        stage('Deploy') {
            steps {
                echo 'Executando aplicação...'
				sh ''' 
					source venv/bin/activate
					python main.py
				'''
            }
        }
    }
}
