pipeline {
  agent none
  stages {
    stage('DEV') {
      steps {
        echo 'Push to QA team'
      }
    }
    stage('Security for DEVS') {
      parallel {
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
      }
    }
    stage('QA') {
      parallel {
        stage('QA') {
          steps {
            echo 'Push To QA Brunch'
          }
        }
        stage('f') {
          agent any
          environment {
            DEV = 'If Fail'
          }
          steps {
            echo 'FAIL'
          }
        }
      }
    }
    stage('Security for QA') {
      parallel {
        stage('validator') {
          steps {
            echo 'Error Found'
          }
        }
        stage('DevOps Approval') {
          steps {
            echo 'Error Found'
          }
        }
        stage('DevSecops Approval') {
          steps {
            echo 'Error Found'
          }
        }
        stage('Team Lead Approval') {
          steps {
            echo 'Error Found'
          }
        }
      }
    }
    stage('PRODUCTION') {
      steps {
        echo 'Push to Main Brunch'
      }
    }
  }
}