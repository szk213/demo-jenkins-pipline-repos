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
        script {
          properties([pipelineTriggers([upstream(
            threshold: hudson.model.Result.SUCCESS,
            upstreamProjects: "demo-jenkins-pipline-repos/test-a")])])
          }

        }
      }
    }
    triggers {
      upstream(threshold: hudson.model.Result.SUCCESS, upstreamProjects: 'demo-jenkins-pipline-repos/test-a')
    }
  }