pipeline {
  agent any

  tools {
    nodejs "NodeJS"   // name you gave in Jenkins config
  }

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test & Security') {
      steps {
        sh 'snyk test'
        sh 'npm install'
        sh 'npm test || echo "No tests defined"'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
        sh 'nohup node index.js &'
      }
    }
  }
}
