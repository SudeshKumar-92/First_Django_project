pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-u root'  // use root to avoid permission issues
        }
    }

    stages {
        stage('Install') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''
                    . venv/bin/activate
                    python manage.py test
                '''
            }
        }
    }
}
