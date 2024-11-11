pipeline {
    agent any
    stages {
        stage('Iniciando ambiente Python') {
            steps {
                // Cria o ambiente virtual
                sh 'python3 -m venv venv'
            }
        }
        stage('Build') {
            steps {
                echo 'Instalando dependências...'
                // Ativa o ambiente virtual e instala as dependências no mesmo comando
                sh 'source venv/bin/activate && pip install -r requirements.txt'
            }
        }
		stage('Deploy') {
			steps {
				echo 'Iniciando e testando aplicação...'
				// Inicia o servidor em segundo plano e captura o PID
				sh 'source venv/bin/activate && python main.py & echo $! > server_pid.txt'
        
				// Aguarda o servidor subir e realiza testes
				sh 'sleep 5 && curl http://localhost:5000/hello'
        
				// Encerra o servidor usando o PID
				sh 'kill $(cat server_pid.txt) && rm server_pid.txt'
			}
		}
    }
}
