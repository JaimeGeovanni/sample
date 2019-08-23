pipeline {
  agent {
    node {
      label 'node 6'
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