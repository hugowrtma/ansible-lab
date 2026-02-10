pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/hugowrtma/ansible-lab.git'
            }
        }

        stage('Deploy with Ansible') {
            steps {
                sh '''
                ansible-playbook ansible/playbook.yml \
                  -i ansible/inventory/hosts.ini \
                  --become
                '''
            }
        }
    }
}
