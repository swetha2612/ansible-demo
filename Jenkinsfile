pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ec2-user-pemfile', inventory: 'hosts', playbook: 'sicte.yml'
            }
        }
    }
}
