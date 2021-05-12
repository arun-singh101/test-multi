pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
    stages {
         stage ('code coverage'){
        steps {
        sh 'echo code testing'
}
}
           
}
}
