pipeline {
  agent none

  stages {
    stage('Test') {
        agent {
            ecs {
                inheritFrom 'esc-test'
            }
        }
        steps {
            sh 'echo hello'
        }
    }
  }
}
