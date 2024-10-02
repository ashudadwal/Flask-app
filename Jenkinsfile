pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/ashudadwal/Flask-app.git'
            }
        }
        stage('Setup Virtual Environment') {
            steps {
                sh 'python3 -m venv venv'  // Create a virtual environment
                sh 'source venv/bin/activate' // Activate the virtual environment
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'bash -c "source venv/bin/activate && pip install -r requirements.txt"' // Install packages in virtual environment
            }
        }
        stage('Run Tests') {
            steps {
                sh 'bash -c "source venv/bin/activate && python -m unittest discover"' // Run tests in virtual environment
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'bash -c "source venv/bin/activate && python app.py"' // Run Flask app in virtual environment
            }
        }
    }
}


