pipeline{
agent any
  tools { 
        maven 'Maven' 
        jdk 'JDK' 
    }
  stages {
   
    stage("build") {
      steps{
        echo "building application"
        bat 'mvn -Dmaven.test.failure.ignore=true install'
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
        bat 'mvn test'
      }
    }
    stage("deploy") {
      steps{
        echo "deploy application"
      }
    }
  }
}
