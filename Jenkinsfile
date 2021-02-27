pipeline {
  agent {
    node {
      label 'Node'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'node --version'
          }
        }

        stage('Docker') {
          steps {
            sh 'docker --version'
          }
        }

      }
    }

    stage('Image') {
      steps {
        sh 'docker build -t image1 .'
      }
    }

  }
}