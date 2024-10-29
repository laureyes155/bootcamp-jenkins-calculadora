pipeline {
agent any
agent { label 'jdk21' }

tools {
maven "maven 3.9.9"
}

stages {
stage('Build') {
steps {
bat 'mvn -B -q package'
}
}
}

}
