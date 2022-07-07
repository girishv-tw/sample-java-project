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
     stage ('trufflehog scan') {
      steps {
          sh 'pwd'
          sh 'echo $PATH'
          sh '/usr/local/bin/trufflehog git file://. --only-verified --json >> truflehog.log'
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
