pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvc clean install'
        }

      }
    }

    stage('Result') {
      steps {
        junit '**/target/surefire-reports/Test-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}
