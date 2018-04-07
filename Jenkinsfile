pipeline {
  agent any
  stages {
    stage('call master branch') {
      parallel {
        stage('call master branch') {
          steps {
            build 'demo-jenkins-pipline-repos/master'
          }
        }
        stage('call master branch2') {
          steps {
            build 'demo-jenkins-pipline-repos/master'
          }
        }
      }
    }
  }
}