pipeline {

  agent { label 'JENKINS_SLAVE' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/kartheek818/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
