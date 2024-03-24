pipeline {
    agent any
    environment {
        // Define environment variables for credentials and key file
        GIT_CREDENTIALS_ID = 'git-credentials'
        EC2_USER_PEMFILE = 'ec2-user-pemfile'
    }
    tools {
        // Ensure ansible is available in this pipeline
        ansible 'ansible'
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the provided GitHub repository
                git credentialsId: "${env.GIT_CREDENTIALS_ID}", url: 'https://github.com/WeLearnWeShare/ansible-demo.git'
            }
        }
        stage('Setup SSH Key') {
            steps {
                // Assuming 'EC2_USER_PEMFILE' is the ID of a secret file credential containing the SSH key
                sshagent(credentials: ["${env.EC2_USER_PEMFILE}"]) {
                    // The SSH key is now available for further steps
                    echo 'SSH key is set up for Ansible'
                }
            }
        }
        stage('Execute Ansible Playbook') {
            steps {
                // Wrap the ansible playbook execution command to colorize the output
                ansiColor('xterm') {
                    sshagent(credentials: ["${env.EC2_USER_PEMFILE}"]) {
                        sh 'ansible-playbook -i inventory playbook.yml'
                    }
                }
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
