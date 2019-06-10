pipeline {
  agent none
  stages {
    stage('Stage 1') {
      parallel {
        stage('Stage 1') {
          steps {
            sh '''docker build --tag helloworld:$BUILD_NUMBER .
docker stop helloworld && docker rm helloworld
docker run --name helloworld -p 1337:1337 helloworld:$BUILD_NUMBER node /var/www/index.js &'''
          }
        }
        stage('Stage 2') {
          steps {
            sh '''docker build --tag helloworld:$BUILD_NUMBER .
docker stop helloworld && docker rm helloworld
docker run --name helloworld -p 1337:1337 helloworld:$BUILD_NUMBER node /var/www/index.js &'''
          }
        }
      }
    }
    stage('') {
      steps {
        echo 'All Done!!!'
      }
    }
  }
  environment {
    var1 = 'Hello World'
    var2 = 'Progressing'
  }
}