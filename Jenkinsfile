pipeline {
    agent any

    stages {
        stage('Clonando um repositório GIT') {
            steps {
                git branch: 'main', url: 'https://github.com/habbema/jk-public-gh.git'
            }
        }
        stage('Buildando uma imagem Docker') {
            steps {
               sh 'docker build -t webapp:${BUILD_NUMBER} .'
            }
        }
        stage('Deploy através de conteiner Docker') {
            steps {
               sh 'docker run --rm -d -p 3200:3000 --name webapp_ctr webapp:${BUILD_NUMBER}'
            }
        }
    }
  }
