
pipeline {
  agent none

  stages {
       stage('PublishAndTests') {
          environment {
              STAGE='prod'
          }
          agent {
            label 'build-python36'
          }
      }
      steps {
        sh 'java -version'
      }
    }
  }

pipeline {
  agent none

  stages {
    stage('Test') {
        agent {
            ecs {
                inheritFrom 'esc-test'
                cpu 2048
                memory 4096
                image 'shatsibed/test:27'
                logDriver 'fluentd'
                logDriverOptions([[name: 'foo', value:'bar'], [name: 'bar', value: 'foo']])
                portMappings([[containerPort: 22, hostPort: 22, protocol: 'tcp'], [containerPort: 443, hostPort: 443, protocol: 'tcp']])
            }
        }
        steps {
            sh 'echo hello'
        }
    }
  }
}
