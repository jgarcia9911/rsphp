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
        stage('construir rsphp'){
           steps{
               sh 'docker build --tag=rsphp .'
               sh 'docker images' 
           }
        } 
        stage('servicio rsphp+rsmysql'){
           steps{
               sh 'sudo /usr/bin/docker-compose up -d'
           }
        }
    }
}
