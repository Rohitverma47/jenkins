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
            touch rohit.txt
            ls -la
            """
          }
        }
    }
    stage('hi') {
      agent {
        kubernetes {
        label 'rohitpod'
        }
      }
        steps {
          container ('ubuntu') {
            sh """
            pwd
            ls -la
            """
          
       }
    }
}
}
}
