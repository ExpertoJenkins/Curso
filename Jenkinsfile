/*
pipeline {
  agent any
  stages {
    stage('Etapa 1') {B
      steps {
              echo 'Hola mundo'
         }
      }
   }
}
*/
node {
  checkout scm
  stage('Compilar') {
    echo "Comienza la compilación..."
    mvn compile
  }
  stage('Test') {
    echo "Comienzan las pruebas..."
  }
  stage('Empaquetar') {
    echo "Comienza la empaquetacion..."
  }
}

