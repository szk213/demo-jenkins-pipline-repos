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
    stage('stage2') {
      steps {
        sh 'echo stage2'
      }
    }
    stage('stage3') {
      steps {
        sh 'echo step1'
      }
    }
  }
  triggers {
    upstream(threshold: hudson.model.Result.SUCCESS, upstreamProjects: "some_project/"+env.BRANCH_NAME.replaceAll("/", "%2F"))
  }
}