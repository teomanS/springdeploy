pipeline {
  agent {
    kubernetes {
      cloud 'aksdev'
      yamlFile 'kubepod.yaml'
    }
  }
    stages { 
    stage('Deploy Application') {
      steps {
        container('deployer') {
          sh 'ls -al'
          sh "kubectl apply -f sampleapp-dep.yaml"
          sh "kubectl apply -f sampleapp-svc.yaml"          
        }
      }
    }
  }
}