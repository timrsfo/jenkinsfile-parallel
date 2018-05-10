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
              docker{ 
                image 'maven:3.3.9-jdk-8-alpine'
              }
            }
            steps {
              echo "On Branch A"
            }
        }
        stage('Branch B') {
          agent { 
            docker { 
              image 'maven:3.3.9-jdk-8-alpine'
            }
          }
          steps {
            echo "On Branch B"
          }
        }
      }
    }
  }
}

