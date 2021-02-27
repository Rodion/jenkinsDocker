pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          agent {
            node {
              label 'node'
            }

          }
          steps {
            sh 'node --version'
          }
        }

        stage('Docker') {
          agent {
            docker {
              image 'docker'
            }

          }
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