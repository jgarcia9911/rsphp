pipeline {
    environment{
      registro="jgarcia9911/rsphp"
      registroID="jgarcia9911_DockerHub"
      dockerImage=""
   }
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
               sh 'sudo docker-compose down'
               sh 'sudo docker system prune -a'
               sh 'sudo docker build --tag=rsphp .'
               sh 'sudo docker images'
               script{
                   dockerImage=docker.build registro
               }
               
           }
        }
        stage('Push a DockerHub'){
             steps{
                script{
                   docker.withRegistry('',registroID){
                      dockerImage.push()
                   }
                }
             }
        }
        stage('servicio rsphp+rsmysql'){
           steps{
               sh 'docker-compose up -d'
           }
        }
    }
}
