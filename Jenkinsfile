pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'managed-node-credential', inventory: 'hosts', playbook: 'site.yml'
            }
        }
    }
}
