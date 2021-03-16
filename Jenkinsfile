pipeline {
    agent none
stages {
    stage('hello') {
      agent {
        kubernetes {
        label 'testpod'
        }
      }
        steps {
          container ('ubuntu') {
            sh """
            pwd
            mkdir rohit
            """
          }
        }
    }
}
}
