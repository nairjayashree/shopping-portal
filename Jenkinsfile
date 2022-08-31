pipeline {
  agent any
  stages {
    stage('compile-app') {
      parallel {
        stage('compile-app') {
          steps {
            echo 'this is the compile job'
            sh 'npm install'
          }
        }

        stage('archive-app') {
          steps {
            archiveArtifacts '**/distribution/*.zip'
          }
        }

      }
    }

    stage('test-app') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
      }
    }

    stage('package-app') {
      steps {
        echo 'this is the package job'
        sh 'npm run package'
      }
    }

    stage('archive-app') {
      steps {
        archiveArtifacts '**/distinguish/*.zip'
        archiveArtifacts '**/distinguish/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'Hey, this is my first pipeline as code...'
    }

  }
}