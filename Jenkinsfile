pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('Checkout git repo'){
            steps {
                dir('kibana-role') {
                    git branch: 'main', credentialsId: '895de364-96f9-4478-99aa-8b1121d7e946', url: 'git@github.com:at6man/kibana-role.git'
                }
            }
        }
        stage('Pip install'){
            steps {
                sh 'pip install -r kibana-role/test-requirements.txt'
            }
        }
        stage('Run molecule'){
            steps {
                dir('kibana-role') {
                    sh 'molecule test'
                }
            }
        }
    }
}