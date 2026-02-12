pipeline {
  agent any
  // will this work?
  //adding another line
 // from bare. worktree
  stages {
    stage('Build') {
      steps {
        echo "Building branch: ${env.BRANCH_NAME}"
        sh 'echo this is build stage'
      }
    }
    //test stage
    stage('Test') {
      steps {
        sh ' echo this is test stage'
      }
    }

    stage('Deploy Dev') {
      when {
        branch 'develop'
      }
      steps {
        sh 'echo this is deploy-dev'
      }
    }

    stage('Deploy Prod') {
      when {
        branch 'main'
      }
      steps {
        echo "this is deploy-prod stage. My branch is : ${env.BRANCH_NAME}"
      }
    }
  }
}


