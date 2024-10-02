pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                // Clones the specified Git repository
                git 'https://github.com/ashudadwal/Flask-app.git'
            }
        }
        stage('Setup Virtual Environment') {
            steps {
                // Create and activate the virtual environment
                sh 'python3 -m venv venv'  
                // Activate the virtual environment in the shell that runs the next commands
                sh 'source venv/bin/activate'
            }
        }
        stage('Install dependencies') {
            steps {
                // Install packages in the virtual environment
                sh 'source venv/bin/activate && pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests in the virtual environment
                sh 'source venv/bin/activate && python -m unittest discover tests'
            }
        }
        stage('Run Flask App') {
            steps {
                // Run Flask app in the virtual environment
                sh 'source venv/bin/activate && python app.py'
            }
        }
    }
}

