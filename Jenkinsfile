pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                sshagent(['your-credential-id']) {
                    sh 'ansible-playbook -i hosts playbook.yml'
                }
            }
        }
    }
}
