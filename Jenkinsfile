pipeline {
    agent any
    triggers { pollSCM('H/5 * * * *') }
    stages {
        stage('Checkout') {
            steps { git branch: 'main', url: 'https://github.com/NavyaChaudhary242/devops-demo.git' }
        }
        stage('Build')  { steps { sh 'echo Building project...' } }
        stage('Test')   { steps { sh 'echo Running tests...' } }
        stage('Deploy') { steps { sh 'echo Deploying application...' } }
    }
}