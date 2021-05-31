pipeline {
       agent { label 'slave01' }
    stages {
        stage('Test') {
             docker { image 'node:14-alpine' }
            steps {
                sh 'node --version'
            }
        }
    
        stage('code coverage') {
            docker { image 'node:14-alpine' }
            steps {
                sh 'echo code testing'
        }
    }
       stage('finalize') {
           docker { image 'node:14-alpine' }
            steps {
                sh 'echo fine'
            }
        }

    stage('Deploy to dev environment'){
            agent { label 'slave01' }
            steps{

          /*  dir('/home/jenkins/deploy/test-multi/'){

                   echo "Shutting down old deployment."
                   sh 'docker-compose down --rmi local'
                   echo "Cleaning the deployment directory."
                   sh 'rm -rf /home/jenkins/deploy/test-multi/* '
                   echo "Checking out new version."
                   checkout scm
                   echo "Building the services."
                   sh 'docker-compose up -d --build --force-recreate'
                   echo "Display services."
                   sh 'docker-compose ps'
                   echo "Done." 
                   }
                   */
            
                sh 'ip a'
                sh 'pwd'
                
      
     }
  }
}
}
