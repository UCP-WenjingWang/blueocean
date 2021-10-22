pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'npm install'
          }
        }

        stage('') {
          steps {
            echo 'build successfully'
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh './jenkins/scripts/test.sh'
          }
        }

        stage('') {
          steps {
            echo 'test successfully'
          }
        }

      }
    }

  }
  environment {
    CI = 'true'
  }
}