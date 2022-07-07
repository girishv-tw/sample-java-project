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
     stage ('trufflehog sca') {
      steps {
          sh 'trufflehog git file://. --only-verified'
          sh 'ls'
      }
     }
    
     stage ('Build') {
      steps {
          sh 'pwd'
          sh 'mvn clean package'
      }
     }
  }
}
