pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo "Building branch: ${env.BRANCH_NAME}"
        sh 'mvn clean package'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('Deploy Dev') {
      when {
        branch 'develop'
      }
      steps {
        sh './deploy-dev.sh'
      }
    }

    stage('Deploy Prod') {
      when {
        branch 'main'
      }
      steps {
        sh './deploy-prod.sh'
      }
    }
  }
}
