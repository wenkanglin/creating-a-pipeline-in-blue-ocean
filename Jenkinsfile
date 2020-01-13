pipeline {
  archiveArtifacts artifacts: '\'module/dist/**/*.zip\'', fingerprint: true

  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm i'
      }
    }

    stage('Build Other') {
      steps {
        build 'simple-node-js-react-npm-app'
      }
    }

  }
}
