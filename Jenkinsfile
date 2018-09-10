pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }

        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }

      }
    }
    stage('Results') {
      steps {
        archiveArtifacts 'target/*.jar'
        junit '**/target/surefire-reports/TEST-*.xml'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
  }
}