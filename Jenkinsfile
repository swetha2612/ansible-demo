pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                ansiblePlaybook credentialsId: 'ec2-user-pemfile', installation: 'ansible', inventory: 'hosts', playbook: 'site.yml'
            }
        }
    }
}
