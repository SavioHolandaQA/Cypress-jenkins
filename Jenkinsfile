pipeline {
    agent {
        docker {
            image 'cypress/browsers:node18.12.0-chrome107-ff107'
            args '-u root'
        }
    }

    environment {
        CYPRESS_RECORD_KEY = credentials('cypress-record-key') // se você tiver um secret no Jenkins
    }

    stages {
        stage('Instalar dependências') {
            steps {
                sh 'npm install'
            }
        }


        stage('Rodar testes Cypress com Cypress Cloud') {
            steps {
                sh 'npm run test'
            }
        }
    }
}
