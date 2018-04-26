pipeline {
  agent any
  stages {
    stage('Non-Parallel Stage') {
      steps {
        echo 'This stage will be executed first.'
      }
    }
    stage('Parallel Stage') {
      failFast true
      parallel {
        stage('Branch A') {
            agent { 
              docker{ image 'alpine:latest' { label "for-branch-a" } }
            }
            steps {
              echo "On Branch A"
            }
        }
        stage('Branch B') {
          agent { 
            docker { image 'alpine:latest' { label "for-branch-b" } }
          }
          steps {
            echo "On Branch B"
          }
        }
      }
    }
  }
}

