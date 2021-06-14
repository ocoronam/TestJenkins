pipeline {
  agent any
  stages {
    stage('Parallel Execution') {
      parallel {
        stage('Shell Script') {
          steps {
            sh 'echo "hello world"'
          }
        }

        stage('build-app') {
          agent {
            docker {
              image 'gradle:6.8.3-jdk11'
            }

          }
          steps {
            sh '`ci/build-app.sh`'
          }
        }

      }
    }

  }
}