pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'false'
        LANG = 'en_US.UTF-8'  // Set UTF-8 encoding
    }
    stages {
        stage('Clone repository') {
            steps {
                // Use GitHub credentials to clone the repository
                git credentialsId: 'github-credentials', url: 'https://github.com/sanjaykshebbar/ASI-Insurance-test.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook playbook: 'ansible-playbook.yml', 
                                inventory: './hosts', 
                                credentialsId: 'ansible-ssh-key'
            }
        }
    }
}

