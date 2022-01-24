podTemplate(cloud: "aksdev", yaml: '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: deployer
    image: lachlanevenson/k8s-kubectl:v1.20.15 
    command:
    - sleep
    args:
    - 99d     
''') {
    node(POD_LABEL) {
        container('deployer') {
            sh "ls -al"
            sh "kubectl apply -f sampleapp-dep.yaml"
            sh "kubectl apply -f sampleapp-svc.yaml"
        }
    }
}
