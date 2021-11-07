pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/magnezone150/jenkins-kubernetes-demo.git', branch:'main'
      }
    }
    
    stage('Deploy App') {
      steps {
        script {
          sh 'kubectl apply -f nginx-deployment.yaml --kubeconfig ~/.kube/config'
        }
      }
    }

  }

}
