pipeline {
    agent any
    stages{  
        stage('paso 1'){
           steps{
               sh 'echo paso 1'
           }
        }
        stage('verificando docker'){
           steps{
               sh 'docker images'
           }
        }
       stage('Construir rsphp'){
           steps{
               sh 'docker-compose down'
               sh 'docker image rm rsphp'
               sh 'docker build --tag=rsphp .'
               sh 'docker images'
           }
        }
        stage('servicio rsphp+rsmysql'){
           steps{
               sh 'docker-compose up -d'
           }
        }
    }
}
