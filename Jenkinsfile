pipeline {
  agent none

  stages {
    stage('Test') {
        agent {
            ecs {
                inheritFrom 'ecs-test'
                cpu 512
                memory 1024
            }
        }
        steps {
            sh 'echo hello'
        }
    }
  }
}
