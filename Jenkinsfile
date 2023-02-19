pipeline{
  agent any
  stages {
    stage('Build'){
      steps{
        sh 'g++ PES1UG20CS456.cpp -o PES1UG20CS456'
        build job : 'PES1UG20CS456-1'
        echo 'Built Successfully!'
      }
    }
    stage('Test'){
      steps{
        sh './PES1UG20CS456'
        echo 'Tested Successfully!'
      }
    }
    stage('Deploy'){
      steps{
        echo 'Deployed successfully'
      }
    }
  }
  post{
    always {
      script {
        if (currentBuild.result == 'FAILURE') {
          echo 'Pipeline build unsuccessful'
        }
      }
    }
  }
}
