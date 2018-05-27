pipeline {
  agent any

  options {
    buildDiscard(logRotator(numToKeepStr: '2', artifactNumtoKeepStr: '1'))
  }

  stages {
    stage('build') {
      steps {
      sh 'ant -f build.xml -v'
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
    }
  }
}
