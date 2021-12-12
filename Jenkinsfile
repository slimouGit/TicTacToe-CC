pipeline{
agent any
  tools { 
        maven 'Maven' 
        jdk 'JDK' 
    }
  stages {
    stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
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
