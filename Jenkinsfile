pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/KafilatAdeleke/math-pytest.git']]])
            }
        }
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/KafilatAdeleke/math-pytest.git'
                sh 'python math_script.py'
            }
        }
        stage('Install') {
            steps {
                sh 'pip install -r requirements.txt' 
            }
        }
        stage('Test') {
            steps {
                sh 'python -m pytest'
            }
        }
    }
}
