pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://your-repository-url.com/ansible-demo.git'
            }
        }
        
        stage('Run Ansible Playbook') {
            steps {
                script {
                    sh 'ansible-playbook -i hosts site.yml'
                }
            }
        }
    }
}
