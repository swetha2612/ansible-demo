pipeline {
    agent any
    stages {
        stage('Color Test') {
            steps {
                script {
                    ansiColor('xterm') {
                        echo '\033[31mThis should be red\033[0m'
                    }
                }
            }
        }
    }
}
