/*
pipeline {
  agent any
  stages {
    stage('Etapa 1') {
      steps {
              echo 'Hola mundo'
         }
      }
   }
}
*/
pipeline {
agent any
  stages {
  stage('Compilar') {
    steps{
    echo "Comienza la compilación..."
   withMaven(
        maven:'Maven por defecto (3.6)'
   ){
      sh 'mvn compile'
   }
  }
}
    
  stage('Test') {
    steps{
    echo "Comienzan las pruebas..."
     withMaven(
        maven:'Maven por defecto (3.6)'
   ){
      sh 'mvn test'
          junit keepLongStdio: true, testResults: '**/*.xml'
   }
  }
  }
    
  stage('Empaquetar') {
     steps{
    echo "Comienza la empaquetacion..."
   withMaven(
       maven:'Maven por defecto (3.6)'
  ){
   // try{
      sh 'mvn package'
    //}finally{
     //deleteDir()
    }
 //   }
  }

