pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'Build'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing..'
          }
        }

        stage('integration testing') {
          steps {
            echo 'integration testing'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Deploy?', ok: 'YES')
        echo 'Deploying...'
      }
    }

  }
}