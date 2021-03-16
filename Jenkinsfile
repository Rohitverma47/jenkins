pipeline {
    agent none
stages {
    stage('hello') {
      agent {
        kubernetes {
        label 'testpod'
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

}
     stage('dotnet') {
       agent {
         kubernetes {
         label 'rohitpod'
        steps {
          container ('dotnet') {
            sh """
            dotnet --version
            """
          }
        }
     }
     }
     }
}
