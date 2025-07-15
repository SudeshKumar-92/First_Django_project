pipeline {
    agent {
        docker {
            image 'python:3.11'
        }
    }

    stages {
        stage('Install and Test') {
            steps {
                sh '''
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    python manage.py test
                '''
            }
        }
    }
}
