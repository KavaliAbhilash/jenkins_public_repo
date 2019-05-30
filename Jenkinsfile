pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'mvn --version'
      }
    }
    stage('Backend') {
      parallel {
        stage('perf') {
          steps {
            build 'TEST_JOB'
          }
        }
        stage('Unit') {
          steps {
            bat 'echo " Unit test"'
          }
        }
      }
    }
    stage('Frontend') {
      steps {
        bat 'echo "frontend"'
      }
    }
    stage('static code analsysis') {
      steps {
        sleep 5
      }
    }
    stage('Deploy') {
      steps {
        bat 'echo "deploy"'
      }
    }
  }
}
