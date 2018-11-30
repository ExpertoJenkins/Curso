node ('master'){ 
    checkout scm
    stage('Compilar') {
	echo "Comienza la compilacion..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn compile'
	}
    }
    stage('Test') {
	echo "Comienzan las pruebas..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn test'
	}
    }
    stage('Empaquetar') {
	echo "Comienza la empaquetacion..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn package'
	}
    }
}










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
/*
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
          junit keepLongStdio: true, testResults: '#poner dos asteriscos#/*.xml'
   }
  }
  }
    
  stage('Empaquetar') {
     steps{
    echo "Comienza la empaquetacion..."
   withMaven(
       maven:'Maven por defecto (3.6)'
  ){
      sh 'mvn package'
   }
  }
  }
    }
  post {
    always{
        deleteDir()
    }
    failure {
      echo "UPS"
    }
    success {
      echo "Exito"
    }
    changed {
      echo 'Cambio'
    }
  }
}
*/

/*
node {
    try {
        stage('Test') {
            sh 'echo "ÉXITO!"; exit 0'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}
*/
