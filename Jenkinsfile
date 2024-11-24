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

  }
}