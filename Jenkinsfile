pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/kmus1232/GipOps will replace by sed command before RUN
        git url: 'https://github.com/kmus1232/GipOps', branch: 'main'
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