pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/lakshmipriyayadav/Poc-7-cicd-ansible.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-image .'
                sh 'docker save -o /home/ubuntu/flask-image.tar flask-image'
            }
        }

        stage('Deploy Using Ansible') {
            steps {
                sh 'ansible-playbook -i ansible/hosts ansible/deploy.yml'
            }
        }
    }
}
