pipeline {
  agent none
  stages {
    stage('Reviewer') {
      steps {
        echo 'Push to QA team'
      }
    }
    stage('Security Steps to qa') {
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
      steps {
        echo 'Push To QA Brunch'
      }
    }
    stage('Security Steps to production ') {
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
    stage('Production') {
      steps {
        echo 'Push to Main Brunch'
      }
    }
  }
}