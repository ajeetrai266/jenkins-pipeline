pipeline {
    agent any
    stages {
        
        stage("terraform-instance") {
            steps {
               git branch: 'main', url: 'https://github.com/ajeetrai266/Terraform-instance.git'
                sh 'sudo terraform init'
                sh 'sudo terraform apply --auto-approve'
                
                /* stash includes: 'inventory', name: 'ansible_inventory' */
                sh 'sudo terraform destroy --auto-approve'
                }
        }
        
        /* stage("ansible-k8s-configure") { 
            steps { 
                git branch: 'main', url: 'https://github.com/ajeetrai266/Ansible-K8s-Cluster.git'
                sh 'sudo ansible all -m ping'
                sh 'sudo ansible-galaxy install -r requirements.yml -p .'
                sh 'sudo ansible-playbook playbook.yml'
            }
        } */
    }
}
