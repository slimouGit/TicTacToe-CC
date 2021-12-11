pipeline{
agent any
  stages {
    stage("build") {
      steps{
        echo "building application"
      }
    }
    stage("test") {
      when {
        expression {
          BRANCH_NAME == 'master'
        }
      }
      steps{
        echo "test application"
      }
    }
    stage("deploy") {
      steps{
        echo "deploy application"
      }
    }
  }
}
