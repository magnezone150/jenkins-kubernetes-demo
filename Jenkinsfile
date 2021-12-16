pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/magnezone150/jenkins-kubernetes-demo.git', branch:'main', credentialsId: 'magnezone150-github'
      }
    }
    
    stage('Deploy App') {
      environment {
        KUBECONFIG = credentials('k8s-cluster')
        NAMESPACE = "magnezoneworld"
      }      
      steps {
        script {
          sh 'ls *.yaml -1 > files'
          sh 'for i in $(cat files); do kubectl apply -f $i -n ${NAMESPACE} --kubeconfig ${KUBECONFIG}; done'
        }
      }
    }
  }
}
