pipeline {
    agent {
        kubernetes {
            label 'testpod'
            defaultContainer 'jnlp'
            yaml """
apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  # Use service account that can deploy to all namespaces
  serviceAccountName: cd-jenkins
  containers:
  - name: golang
    image: golang:1.10
    command:
    - cat
    tty: true
  - name: gcloud
    image: gcr.io/cloud-builders/gcloud
    command:
    - cat
    tty: true
  - name: ubuntu
    image: ubuntu:18.04
    command:
    - cat
    ttyl: true  
  - name: kubectl
    image: gcr.io/cloud-builders/kubectl
    command:
    - cat
    tty: true
"""
        }
    }
stages {
    stage(hello) {
        steps {
          container(ubuntu) {
              sh """
              pwd
              mkdir rohit
              """
          }    
        }
    }

}    
}
