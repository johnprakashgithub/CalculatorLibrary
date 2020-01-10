pipeline {
   agent {
       docker {image '3.7-alpine3.10'}
   }

   stages {
      stage('Build') {
        steps {
          echo 'Building...'
          echo "Running ${env.BUILD_ID} ${env.BUILD_DISPLAY_NAME} on ${env.NODE_NAME} and JOB ${env.JOB_NAME}"
          python3 -m venv venv
          . venv/bin/activate
          pip install -r requirements.txt
          flake8 --exclude=venv* --statistics
          pytest -v --cov=calculator
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