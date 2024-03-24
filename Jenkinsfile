pipeline {
    agent any

    options {
        ansiColorBuildWrapper('xterm')
    }

    stages {
        stage('Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ec2-user-pemfile', disableHostKeyChecking: true, installation: 'ansible', inventory: 'inventory', playbook: 'playbook.yml', colorized: true
            }
        }
    }
}
