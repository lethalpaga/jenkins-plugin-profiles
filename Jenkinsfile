def name = "test"
if(env.BRANCH_NAME == "master") {
    name = "master"
}

pipeline {
  agent any

  parameters {
      string(name: 'PERSON', defaultValue: name, description: 'Who should I say hello to?')
  }

  stages {
    stage('Test') {
      steps {
        sh 'echo Test successful'
        catchError() {
          echo "This is a test ${params.PERSON}"
        }
      }
    }
  }
}