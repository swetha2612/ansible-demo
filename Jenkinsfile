pipeline {
    agent any

    environment {
        GITHUB_CREDS = credentials('git-credentials') // Replace 'github-credentials-id' with your actual credential ID
        HOST_CREDS = credentials('ec2-user-pemfile') // Replace 'host-credentials-id' with your actual credential ID
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: "${GITHUB_CREDS}",
                    url: 'https://github.com/WeLearnWeShare/ansible-demo.git'
            }
        }

        stage('Deploy') {
            steps {
                ansiColor('xterm') {
                    sh '''
                        export ANSIBLE_FORCE_COLOR=true
                        ansible-playbook --private-key=$HOME/.ssh/id_rsa \
                                         --user=ec2-user \
                                         --become \
                                         -i hosts \
                                         site.yml
                    '''
                }
            }
        }
    }
}
