pipeline {
  agent none
  stages {
    stage('Dev') {
      parallel {
        stage('Security Steps') {
          steps {
            build 'Developer'
          }
        }
        stage('Reviewer') {
          steps {
            catchError()
          }
        }
        stage('DevOps Approval') {
          steps {
            echo 'approved'
          }
        }
      }
    }
    stage('QA') {
      parallel {
        stage('Security Steps') {
          steps {
            echo 'qa'
          }
        }
        stage('Validator') {
          steps {
            error 'Error find'
          }
        }
        stage('DevOps Approval') {
          steps {
            echo 'Error find'
          }
        }
        stage('Devsecops Approval') {
          steps {
            echo 'approved'
          }
        }
        stage('Team Lead Approval') {
          environment {
            Dev = 'true'
          }
          steps {
            echo 'Team lead approval'
          }
        }
      }
    }
    stage('Production') {
      steps {
        echo 'production done'
      }
    }
  }
}