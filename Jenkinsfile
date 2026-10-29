pipeline {
    agent any
    stages {
        stage('Checkout') { steps { git branch: 'main', url: 'https://github.com/NavyaChaudhary242/devops-demo.git' } }
        stage('Test') {
            steps { sh 'python3 -m venv venv && . venv/bin/activate && pip install -q pytest && pytest -v' }
        }
        stage('Deploy') {
            steps { sh 'mkdir -p /var/jenkins_home/deploy && cp calc.py /var/jenkins_home/deploy/' }
        }
    }
    post {
        success { echo 'Tests passed - application deployed.' }
        failure { echo 'Tests failed - deployment skipped.' }
    }
}