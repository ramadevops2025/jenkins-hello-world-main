pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*'
      }
    }

    stage('Maven Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST*.xml*', keepProperties: true, keepTestNames: true)
      }
    }

  }
  tools {
    maven 'm398'
  }
}