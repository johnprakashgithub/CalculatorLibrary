pipeline {
   agent any

   stages {
      
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${env.BUILD_ID} ${env.BUILD_DISPLAY_NAME} on ${env.NODE_NAME} and JOB ${env.JOB_NAME}"
          sh 'python3 -m venv venv && . venv/bin/activate && pip install -r requirements.txt'
        }
   }
      stage('unittest') {
        steps {
          echo 'Unit test...'
          sh '. venv/bin/activate && flake8 --exclude=venv* --statistics && pytest -v --cov=calculator'
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
