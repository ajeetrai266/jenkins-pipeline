pipeline {
    agent any
    stages {
        stage("tf-code") {
            steps {
               git branch: 'main', url: 'https://github.com/ajeetrai266/Terraform.git'
            }
        }
        stage("tf") {
            steps {
                sh 'terraform init'
                sh 'sudo terraform apply -auto-approve'
            }
        }
        stage("playbook-run") {
            steps {
                ansiblePlaybook installation: 'ansible-1', playbook: 'playbook.yml'
            }
        }
    }
}
