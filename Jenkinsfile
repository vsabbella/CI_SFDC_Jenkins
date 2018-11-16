pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        bat 'SET ANT_HOME=.\\build\\ant\\apache-ant-1.10.5'
      }
    }
    stage('Build') {
      steps {
        bat 'ant deployUnpackaged'
      }
    }
    stage('finalize') {
      steps {
        emailext(subject: 'Build Susccessful', body: 'The build is successful', attachLog: true, to: 'vsabbella@informatica.com')
      }
    }
  }
}