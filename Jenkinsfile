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
            echo hirohit > rohit.txt
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
            cat /home/jenkins/agent/workspace/pipe/rohit.txt
            """
          
       }
    }
}
}
}
