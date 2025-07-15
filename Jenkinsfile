pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-u root' // ensures root user in container
        }
    }

    stages {
        stage('Install') {
            steps {
                sh '''
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }
    }
}
