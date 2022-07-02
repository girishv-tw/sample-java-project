pipeline {
  agent any
  stages {
  stage('Check out') {
      steps {
        script {
          git clone https://github.com/anuragpathak2608/sample-java-project
          cd sample-java-project
          mvn -B package --file pom.xml
          go version
          pwd
        }
      }
    }
  stage('Stage 2') {
      steps {
        script {
          echo 'Stage 2'
        }
      }
    }
  }
}
