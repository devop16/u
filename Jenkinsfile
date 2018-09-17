pipeline {
  agent none
  stages {
    stage('Reviewer') {
      steps {
        echo 'Push to QA team'
      }
    }
    stage('Security Steps') {
      parallel {
        stage('Validator') {
          steps {
            echo 'Error Found'
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
    stage('QA') {
      parallel {
        stage('Production') {
          steps {
            echo 'production done'
          }
        }
        stage('Validator') {
          steps {
            echo 'Error Found'
          }
        }
        stage('Devops Approval') {
          steps {
            echo 'Error found'
          }
        }
        stage('DevSecOps Approval') {
          steps {
            waitForQualityGate true
          }
        }
        stage('Team Lead Approval') {
          steps {
            echo 'error found'
          }
        }
      }
    }
    stage('Production') {
      steps {
        echo 'Appproved'
      }
    }
  }
}