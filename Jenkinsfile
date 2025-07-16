pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh '''
                    python3.10 -m venv /tmp/myvenv
                    . /tmp/myvenv/bin/activate
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                dir('First_Django_project') {
                    sh '''
                        . /tmp/myvenv/bin/activate
                        python manage.py test
                    '''
                }
            }
        }
    }
}
