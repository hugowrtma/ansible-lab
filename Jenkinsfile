pipeline {
  agent any

  triggers {
    githubPush()
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Ping Host') {
      steps {
        sh 'ansible all -m ping'
      }
    }

    stage('Deploy') {
      steps {
        sh 'ansible-playbook ansible/playbooks/deploy.yml'
      }
    }
  }
}
