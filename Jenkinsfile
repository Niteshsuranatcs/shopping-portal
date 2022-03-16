pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        echo 'this is the Compile first job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the Test second job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the Package third job'
        sh 'npm run package'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}