pipeline {
    /* agent {
        docker { image 'python:3' }
    } */
/*    agent any */
    agent {
      kubernetes {
        label 'muhpod'
        defaultContainer 'jnlp'
        cloud 'Kubernetes'
        inheritFrom 'docker-build-slave'
        yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: python3
    image: python:3.6
    command:
    - cat
    tty: true

"""

      }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

