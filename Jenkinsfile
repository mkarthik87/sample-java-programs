pipeline {
  agent none
  stages {
    stage('build initialization') {
      agent {
        docker {
          image 'maven:3-alpine'
          args '-v /root/.m2:/root/.m2'
        }

      }
      steps {
        sh 'mvn clean compile'
      }
    }

  }
  post {
    success {
      echo 'Build success'
    }

    failure {
      echo 'Build failed'
    }

  }
}