pipeline {
  agent {
    dockerfile {
      filename 'Dockerfile'
    }
  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'python3 main.py'
          }
        }
      }
    }


    stage('html') {
      steps {
        publishHTML(target: [allowMissing: false,
                                alwaysLinkToLastBuild: true,
                                keepAll: true,
                                reportDir: 'reports',
                                reportFiles: '*.html',
                                reportName: 'My Reports',
                                reportTitles: 'The Report'])
      }
    }
  }
}
