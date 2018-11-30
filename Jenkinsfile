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
//    withMaven(
//        maven:'Maven por defecto (3.6)'
//    ){
      sh 'mvn compile'
//    }
  }
  stage('Test') {
    echo "Comienzan las pruebas..."
//     withMaven(
//        maven:'Maven por defecto (3.6)'
//    ){
      sh 'mvn test'
//    }
  }
  stage('Empaquetar') {
    echo "Comienza la empaquetacion..."
 //   withMaven(
 //       maven:'Maven por defecto (3.6)'
  //  ){
    try(
      sh 'mvn package'
      )finally(
        deleteDir()
      )
 //   }
  }
}

