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
                image 'maven:3.5.3-jdk-8-alpine'
              }
            }
            steps {
              sh 'mvn -v'
            }
        }
        stage('Branch B') {
          agent { 
            docker { 
              image 'maven:3.5.3-jdk-8-alpine'
            }
          }
          steps {
              sh 'mvn -v'
          }
        }
      }
    }
  }
}

