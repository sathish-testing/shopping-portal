pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        echo 'this is the first job'
        sh 'npm install'
      }
    }

    stage('test') {
      steps {
        echo 'this is the second job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
      }
    }

    stage('archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

    stage('Deploy to Prod') {
      steps {
        build 'ansible-playbook frontend.yml'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this is my first pipeline has completed...'
    }

  }
}