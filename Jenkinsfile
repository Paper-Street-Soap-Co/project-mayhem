pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('Parallel Tests') {
      failFast true
      parallel {
        stage('pytest') {
          steps {
            echo "On Branch A"
          }
        }
        stage('webdriver') {
          steps {
            echo "On Branch B"
          }
        }
      }
    }
    stage("Update Repos") {
      failFast true
      parallel {
        stage("docker push") {
          steps {
            echo "blah"
          }
        }
        stage("helm serve") {
          steps {
            echo "blah"
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying..'
      }
    }
    stage('Validate') {
      steps {
        echo 'Validate..'
      }
    }
  }
}
