pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn --version'
      }
    }
    stage('Backend') {
      parallel {
        stage('perf') {
          steps {
            sh 'echo "perf"'
          }
        }
        stage('Unit') {
          steps {
            sh 'echo " Unit test"'
          }
        }
      }
    }
    stage('Frontend') {
      steps {
        sh 'echo "frontend"'
      }
    }
    stage('static code analsysis') {
      steps {
        sleep 5
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "deploy"'
      }
    }
  }
}
