pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh '''
                python3.10 -m venv venv
                source venv/bin/activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                dir('Django_project') { // <-- this must be the project root dir
                    sh '''
                    source ../venv/bin/activate
                    python manage.py test
                    '''
                }
            }
        }
    }
}
