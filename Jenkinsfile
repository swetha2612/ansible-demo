pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                script {
                    ansiColor('xterm') {
                        sh 'export ANSIBLE_FORCE_COLOR=true && ansible-playbook -i hosts site.yml'
                    }
                }
            }
        }
    }
}
