pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh '''
                    if [ ! -d "venv" ]; then
                    python3.10 -m venv venv
                    fi
                '''
                }
                        }

        stage('Test') {
            steps {
                dir('Django_project') { // <-- this must be the project root dir
                    sh '''
                    bash -c "source venv/bin/activate &&
                    python manage.py test "
                    '''
                }
            }
        }
    }
}
