pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }
    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
        emailext(subject: 'Aprobar', to: 'Geovanni', body: 'Por favor aprobar')
      }
    }
    stage('Approve') {
      steps {
        input(message: 'Se aprueba?', submitter: 'Geovanni')
      }
    }
    stage('Deploy') {
      steps {
        echo 'HECHO!!!!'
      }
    }
  }
}