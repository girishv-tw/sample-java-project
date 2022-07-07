pipeline {
  agent any 
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Initialize') {
      steps {
        sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            ''' 
      }
    }
     stage ('Build') {
      steps {
          sh 'pwd'
          sh 'mvn clean package'
      }
     }
          post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
            }
     
  }
}
