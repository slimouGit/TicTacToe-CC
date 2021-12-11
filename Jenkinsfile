pipeline{
agent any
  stages {
    stage("build") {
      steps{
        echo "building application"
        sh 'mvn -B -DskipTests clean package'
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
