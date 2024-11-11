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
                echo 'Executando aplicação...'
                // Ativa o ambiente virtual e executa a aplicação no mesmo comando
                sh 'source venv/bin/activate && timeout 20 python main.py'
            }
        }
    }
}
