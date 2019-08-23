pipeline {
  agent {
    node {
      label 'node'
    }

  }
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
  }
}