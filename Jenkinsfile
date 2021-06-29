pipeline {
    agent any
    stages {
        stage("terraform-instance") {
            steps {
               git branch: 'main', url: 'https://github.com/ajeetrai266/Terraform-instance.git'
            }
            steps {
                sh 'sudo terraform init'
                sh 'sudo terraform apply --auto-approve'
            }
        }
    }
}
