pipeline {
  agent any
  parameters {
        string(name: 'SVNCHKOUTURL', defaultValue: 'https://acm.ultimatix.net/svn/Ultimatix_EAG/Project/DevOpsCoE/DevOpsSrc/CR_DevOpsPilot/SourceCode/ALTReports', description: 'Enter your SVN url')
    }
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
            build job: 'TEST_JOB' , parameters:[ string(name: 'VALUE_NAME',value: "${params.SVNCHKOUTURL}") ]
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
