pipeline {

  agent { label 'kube-jenkins' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/magnezone150/jenkins-kubernetes-demo.git', branch:'main'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx-deployment.yaml", kubeconfigId: "kubeconfig")
        }
      }
    }

  }

}
