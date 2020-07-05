pipeline {
  agent {
    docker {
      image 'node:latest'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
	sh 'sudo npm install yarn --registry=https://registry.npm.taobao.org'
	sh 'yarn config set registry https://registry.npm.taobao.org -g'
	sh 'yarn config set sass_binary_site http://cdn.npm.taobao.org/dist/node-sass -g'
        sh 'yarn install'
      }
    }

  }
}
