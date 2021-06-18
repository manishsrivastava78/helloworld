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
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Deploy?', ok: 'YES')
            echo 'Deploying...'
          }
        }

        stage('SendNotification') {
          steps {
            mail(subject: 'Approval for deployment', body: 'Request you to please provide your go ahead for the release to <br> deploy in the production environent.', to: 'manishsrivastava0409@gmail.com')
          }
        }

      }
    }

  }
}