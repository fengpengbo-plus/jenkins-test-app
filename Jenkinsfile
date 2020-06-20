pipeline {
   agent {
  	docker 'node:6.3' 
   }
   stages {
        stage('Build') { 
            steps {
                sh 'yarn install' 
            }
        }
    }
}
