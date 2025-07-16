pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh '''
                python3.10 -m venv venv || (echo "Failed to create venv"; exit 1)
                source venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                dir('Django_project') { // <-- this must be the project root dir
                    sh '''
                    . /venv/bin/activate
                    python manage.py test
                    '''
                }
            }
        }
    }
}
