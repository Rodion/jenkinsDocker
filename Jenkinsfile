pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Node') {
          agent {
            docker {
              image 'node'
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
      agent {
        docker {
          image 'image1'
        }

      }
      steps {
        sh '''checkout scm

def customImage = docker.build("image1")
customImage.inside {
   sh \'make test\'
}
'''
      }
    }

  }
}