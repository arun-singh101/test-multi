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

            dir('/home/ubuntu/deploy/GRUI/'){

                   echo "Shutting down old deployment."
                   sh 'docker-compose -p grui-dev down --rmi local'
                   echo "Cleaning the deployment directory."
                   sh 'rm -rf /home/ubuntu/deploy/GRUI/* '
                   echo "Checking out new version."
                   checkout scm
                   echo "Building the services."
                   sh 'docker-compose -p grui-dev up -d --build --force-recreate'
                   echo "Display services."
                   sh 'docker-compose -p grui-dev ps'
                   echo "Done."
      }
     }
  }
}
}
