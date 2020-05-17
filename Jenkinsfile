pipeline {
  agent none

  stages {
    stage('Test') {
        agent {
            ecs {
                inheritFrom 'ecs-test'
            }
        }
        steps {
            sh 'echo hello'
        }
    }
  }
}
