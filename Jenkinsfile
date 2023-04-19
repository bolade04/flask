pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/bolade04/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t bolade4/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u bolade4 -p dckr_pat__ybsNSmfPt4kju3wLAE6dHoiDH4'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push bolade4/flask_app'
      }
    }

  }
}