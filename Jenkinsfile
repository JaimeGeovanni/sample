pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'node:6-alpine'
    }

  }
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
    //stage('Approve') {
    //  steps {
    //    input(message: 'Se aprueba?', submitter: 'Geovanni')
    //  }
    //}
    stage('Deploy to development') {
      when{
        branch 'deployment'
      }
      steps {
        echo 'HECHO EN DESARROLLO!!!!'
      }
    }
    stage('Deploy to production') {
      when{
        branch 'production'
      }
      steps {
        echo 'HECHO EN PRODUCCIÓN!!!!'
      }
    }
    stage('Deploy to master') {
      when{
        branch 'master'
      }
      steps {
        echo 'HECHO EN MASTER!!!!'
      }
    }
  }
}
