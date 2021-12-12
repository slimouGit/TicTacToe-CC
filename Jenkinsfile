pipeline{
agent any
  tools { 
        maven 'Maven' 
        jdk 'JDK' 
    }
  stages {
   
    stage("clean") {
      steps{
        echo "clean application"
        bat 'mvn clean -D skipTests'
      }
    }
    
    stage("build") {
      steps{
        echo "building application"
        bat 'mvn -Dmaven.test.failure.ignore=true install'
      }
    }
    
    stage("compile") {
      steps{
        echo "compile application"
        bat 'mvn compile'
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
