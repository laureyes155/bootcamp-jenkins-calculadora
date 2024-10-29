pipeline {
  agent any

  tools {
    maven "maven 3.9.9"
  }

  parameters {
    string(name: 'CONTRASENA', defaultValue: 'esta_es_mi_contra', description: 'Ingresar contrasenia')
  }

  stages {
    stage ('ejemplo') {
      steps {
        echo params.CONTRASENA
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
