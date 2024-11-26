pipeline {
  agent {
    docker {
      image 'maven:3.9.9-eclipse-temurin-17'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/JianengHuang/simple-java-maven-app.git', branch: 'master')
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean packages'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'mvn test'
          }
        }

        stage('Test2') {
          steps {
            sh 'mvn test'
          }
        }

      }
    }

    stage('Archive artifacts') {
      steps {
        archiveArtifacts(artifacts: '**/target/*.jar', fingerprint: true)
      }
    }

  }
  environment {
    API_KEY = '1234'
  }
}