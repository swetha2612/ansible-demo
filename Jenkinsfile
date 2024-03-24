pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-credentials', url: 'https://github.com/WeLearnWeShare/ansible-demo.git'
            }
        }

        stage('Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ec2-user-pemfile', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts', playbook: 'site.yml', colorized: true
            }
        }
    }
}
