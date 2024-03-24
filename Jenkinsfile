pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                script {
                    ansiColor('xterm') {
                        ansiblePlaybook credentialsId: 'ec2-user-pemfile', disableHostKeyChecking: true, installation: 'ansible', inventory: 'hosts', playbook: 'site.yml'
                    }
                }
            }
        }
    }
}
