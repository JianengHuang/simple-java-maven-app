pipeline {
  agent {
    docker {
      image 'maven:3.8.5-openjdk-17'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/JianengHuang/simple-java-maven-app', branch: 'master')
      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo hola'
          }
        }

        stage('Log') {
          steps {
            sh 'echo adios'
          }
        }

      }
    }

    stage('Test') {
      steps {
        sh 'echo test'
      }
    }

    stage('Build artifacts') {
      steps {
        sh 'echo hello'
      }
    }

  }
}