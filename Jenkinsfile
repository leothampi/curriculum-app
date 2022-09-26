pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/leothampi/curriculum-app/', branch: 'dev')
      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build_1') {
      steps {
        sh 'docker build github.com/creack/docker-firefox'
      }
    }

    stage('Log into Dockerhub') {
      environment {
        DOCKERHUB_USER = 'fuze365'
        DOCKERHUB_PASSWORD = 'gv1&3Ea9W##onDQAMUG&41CvZ7h1d1'
      }
      steps {
        sh 'docker login -u $DOCKERHUB_USER -p $DOCKERHUB_PASSWORD'
      }
    }

  }
}
