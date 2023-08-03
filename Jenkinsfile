pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/hyungs77/GitOPs.git will replace by sed command before RUN
        git url: 'https://github.com/hyungs77/GitOPs.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}