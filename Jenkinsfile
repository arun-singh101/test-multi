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
           # when { branch "master" }
            steps{

            dir('/home/jenkins/deploy/test-multi/'){

                   echo "Shutting down old deployment."
                   sh 'docker-compose -p web down --rmi local'
                   echo "Cleaning the deployment directory."
                   sh 'rm -rf /home/ubuntu/deploy/test-multi/* '
                   echo "Checking out new version."
                   checkout scm
                   echo "Building the services."
                   sh 'docker-compose -p web up -d --build --force-recreate'
                   echo "Display services."
                   sh 'docker-compose -p web ps'
                   echo "Done."
      }
     }
  }
}
}
