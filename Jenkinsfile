pipeline {
       agent { label 'slave01' }
    stages {
        stage('Test') {
             agent {
             docker { image 'node:14-alpine' }
        }
      steps {
                sh 'node --version'
            }
    }
           
            stage('deployment on dev') {
             agent { label 'slave01' }
               
           steps{
                dir('/home/jenkins/deploy/test-multi'){
                    echo "Shutting down old deployment."
                    sh 'docker-compose down --rmi local'
                    echo "Cleaning the deployment directory."
                    sh 'rm -rf /home/jenkins/deploy/test-multi/*'
                    echo "Checkout new version."
                    checkout scm
                    sh 'docker-compose up -d --build --force-recreate'
                    echo "Display services."
                    sh 'docker-compose  ps'
                    echo "Done."
                }
                  
           }
         
                   
            }
           
    }
}
