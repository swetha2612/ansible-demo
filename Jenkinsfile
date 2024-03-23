pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                sshagent(['managed-node']) {
                    sh 'ansible-playbook -i hosts site.yml'
                }
            }
        }
    }
}
