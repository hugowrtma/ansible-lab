pipeline {
  agent any

  options {
    timestamps()
  }

  stages {
    stage('Check Ansible') {
      steps {
        sh 'ansible --version'
      }
    }

    stage('Ping Host') {
      steps {
        sh 'ansible all -m ping'
      }
    }

    stage('Deploy') {
      steps {
        sh 'ansible-playbook playbooks/deploy.yml'
      }
    }
  }
}
