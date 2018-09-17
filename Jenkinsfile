pipeline {
  agent none
  stages {
    stage('DEV') {
      steps {
        echo 'Push to QA team'
      }
    }
    stage('Security for DEV') {
      parallel {
        stage('DevOps Approval') {
          steps {
            echo 'Error find'
          }
        }
        stage('Reviewer') {
          steps {
            echo 'approved'
          }
        }
      }
    }
    stage('QA') {
      steps {
        echo 'Push To QA Brunch'
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