pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        // Use SSH Agent for GitHub checkout
        sshagent(credentials: ['git-credentials	']) {
          git url: 'git@github.com:WeLearnWeShare/ansible-demo.git'
        }
      }
    }
    stage('Deploy to Managed Node') {
      steps {
        // Use SSH Agent to run commands on a managed node
        sshagent(credentials: ['ec2-user-pemfile']) {
          sh 'ssh user@managed_node_address ansible-playbook -i inventory_file playbook.yml'
        }
      }
    }
  }
}
