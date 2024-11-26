pipeline {
  agent {
    docker {
      image 'maven:3.9.9-eclipse-temurin-17'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/JianengHuang/simple-java-maven-app.git'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package'
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

    stage('Archive Artifacts') {
      steps {
        archiveArtifacts(artifacts: '**/target/*.jar', fingerprint: true)
      }
    }

  }
}