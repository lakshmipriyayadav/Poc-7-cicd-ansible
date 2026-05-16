pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'YOUR_GITHUB_REPO_URL'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-image .'
            }
        }

        stage('Deploy Using Ansible') {
            steps {
                sh 'ansible-playbook -i ansible/hosts ansible/deploy.yml'
            }
        }
    }
}