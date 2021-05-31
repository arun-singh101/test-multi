pipeline {
       agent { label 'slave01' }
    stages {
        stage('Test') {
             agent {
             docker { image 'node:14-alpine' }
        }
      }
      steps {
                sh 'node --version'
            }
      }
    
}
