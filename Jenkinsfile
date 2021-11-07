pipeline {

  agent any

  stages {

    stage('Deploy App') {
      steps {
        script {
          sh 'kubectl apply -f nginx-deployment.yaml'
        }
      }
    }

  }

}
