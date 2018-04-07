pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            sh 'echo step1'
          }
        }
        stage('p-stage1') {
          steps {
            sh 'echo p-stage step1'
          }
        }
      }
    }
  }
}