pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/Zied-BenBahri/jenkins-maven-demo.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -v'
        sh 'mvn -B -e clean package'
      }
    }
    stage('Tests') {
      steps {
        junit 'target/surefire-reports/*.xml'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
      }
    }
  }
}
