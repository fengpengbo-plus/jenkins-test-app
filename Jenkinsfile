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
        sh 'yarn install'
        sh '''#!/bin/sh
#
DATE=`date +%m%d%H%M `
#DIR="/Users/fengpengbo/jenkins/jobs/nginx/workspace/"
 DIR="."
sudo /usr/local/bin/docker build -t nginx_$DATE $DIR | tee $DIR/Docker_build_result.log
 
RESULT=$(cat $DIR/Docker_build_result.log | tail -n 1)
 
if [["$RESULT" != *Successfully*]];then
  exit -1
fi'''
      }
    }

  }
}