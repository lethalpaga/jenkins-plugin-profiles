env.PERSON = "test"
if(env.BRANCH_NAME == "master") {
    env.PERSON = "master"
}

pipeline {
  agent any

  // This is want we want to achieve
//   profiles {
//       profile("test") {
//           environment {
//           }

//           parameters {
//           }
//       }
//   }

  parameters {
      string(name: 'PERSON', defaultValue: env.PERSON, description: 'Who should I say hello to?')
  }

//   triggers {
      
//   }

  stages {
    stage('Test') {
      steps {
        sh 'echo Test successful'
        catchError() {
          echo '"This is a test ${params.PERSON}"'
        }
        
      }
    }
  }
}