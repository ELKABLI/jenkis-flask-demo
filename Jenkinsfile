pipeline {
    agent {
      docker {
        image 'python:3'
      }
    }
    stages {
        stage('Clone repo') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/ELKABLI/jenkis-flask-demo.git', branch: 'main'
            }
        }
       stage('Test') {
            steps {
              withEnv(["HOME=${env.WORKSPACE}"]) {
                sh """
                echo ${env.WORKSPACE}
                python --version
                pip install -r requirements.txt
                python -m pytest
                """
              }
            }
        }
    }
}

