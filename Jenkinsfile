pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        }
    }
    stage('Test') {
      steps {
        echo 'Testing'
      }
    }
    stage('Sanity check') {
      input {
        message 'Should we continue?'
        id 'Yes, we should.'
        submitter 'demoyan'
        parameters {
          choice(name: 'Components', choices: ['cmc', 'rmc', 'cd'], description: 'choose the component')
        }
      }
      steps {
        input 'Does the staging environment look ok?'
      }
    }
  }
}