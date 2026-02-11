pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo "Building branch: ${env.BRANCH_NAME}"
        //sh 'mvn clean package'
        sh 'echo this is build stage'
      }
    }

    stage('Test') {
      steps {
        //sh 'mvn test'
        sh ' echo this is test stage'
      }
    }

    stage('Deploy Dev') {
      when {
        branch 'develop'
      }
      steps {
        //sh './deploy-dev.sh'
        sh 'echo this is deploy-dev'
      }
    }

    stage('Deploy Prod') {
      when {
        branch 'main'
      }
      steps {
        //sh './deploy-prod.sh'
        sh 'this is deploy-prod stage'
      }
    }
  }
}


