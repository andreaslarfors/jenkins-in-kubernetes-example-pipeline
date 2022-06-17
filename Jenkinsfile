pipeline {
  agent {
    kubernetes {
      yaml '''
        apiVersion: v1
        kind: Pod
        spec:
          containers:
          - name: busybox
            image: busybox
            command:
            - cat
            tty: true
            resources:
              requests:
                memory: "2Gi"
                cpu: "1000m"
        '''
    }
  }
  stages {
    stage('Run') {
      steps {
        container('busybox') {
          sh '/bin/busybox'
        }
      }
    }
  }
}