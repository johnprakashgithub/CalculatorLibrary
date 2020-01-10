pipeline {
   agent any

   stages {
      
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${env.BUILD_ID} ${env.BUILD_DISPLAY_NAME} on ${env.NODE_NAME} and JOB ${env.JOB_NAME}"
          sudo python3 -m venv venv
          sudo . venv/bin/activate
          sudo pip install -r requirements.txt
        }
   }
      stage('unittest') {
        steps {
          echo 'Unit test...'
          sudo . venv/bin/activate
          sudo flake8 --exclude=venv* --statistics
          sudo pytest -v --cov=calculator
        }
   }
   stage('Test') {
     steps {
        echo 'Testing...'
     }
   }
   stage('Deploy') {
     steps {
       echo 'Deploying...'
     }
   }
  }
}
