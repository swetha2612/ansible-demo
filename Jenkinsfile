pipeline {
    agent any

    stages {
        stage('Ansible Playbook') {
            steps {
                // Wrap your shell step or ansiblePlaybook plugin call with ansiColor
                ansiColor('xterm') {
                    sh '''
                    ansible-playbook -i hosts site.yml \
                                     --private-key /var/lib/jenkins/workspace/test_job/ssh4200161842676383069.key \
                                     -u ec2-user
                    '''
                }
            }
        }
    }
}
