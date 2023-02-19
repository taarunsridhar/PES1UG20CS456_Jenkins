pipeline {
agent any
  
stages {
    stage('Build') {
        steps {
            sh 'g++ -o PES1UG20CS456-1 PES1UG20CS456.cpp'
        }
    }

    stage('Test') {
        steps {
            sh './PES1UG20CS456'
        }
    }

    stage('Deploy') {
        steps {
            echo 'Deployment successful!'
        }
    }
}

post {
    always {
        script {
            if (currentBuild.result == 'FAILURE') {
                echo 'Pipeline failed!'
            }
        }
    }
}
}
