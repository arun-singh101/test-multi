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
    
        stage('code coverage') {
            steps {
                sh 'echo code testing'
        }
    }
       stage('finalize') {
            steps {
                sh 'echo fine'
            }
        }
    stage('Deploy to dev environment'){
            agent { label 'slave01' }
            when { branch "master" }
            steps{
                    sh 'echo outofdocker'
      }
  }
}
