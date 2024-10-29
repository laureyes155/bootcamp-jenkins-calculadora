pipeline {
  agent any

  tools {
    maven "maven 3.9.9"
  }

  parameters {
    string(name: 'ENTRADA', defaultValue: 'Hola', description: 'Un parametro requerido')
  }

  stages {
    stage ('ejemplo') {
      steps {
        echo params.ENTRADA
      }
    }
    stage('Build') {
      steps {
        bat 'mvn -B -q package'
      }
      post {
        always {
          junit 'target/surefire-reports/*.xml'
        }
      }
    }
  }

}
