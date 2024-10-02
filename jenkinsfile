pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/ashudadwal/Flask-app.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'python3 -m unittest discover tests'
            }
        }
        stage('Run Flask App') {
            steps {
                sh 'python3 app.py'
            }
        }
    }
}
