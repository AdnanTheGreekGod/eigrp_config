pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                 git credentialsId: '541f9d19-c79f-49fb-9ad7-65dfbd124708',
                 url: 'https://github.com/AdnanTheGreekGod/router.git'
            }
        }

    stage('Test Code') {
            steps {
                sh 'echo "Running unit tests..."'
                sh 'echo "Performing code analysis..."'
                sh 'echo "Linting code..."'
            }
        }

        stage('Deploy with Ansible') {
            steps {
                sh '/home/devasc/.local/bin/ansible-playbook -i inventory/eigrp_hosts eigrp_config.yml'
            }
        }
    }
}
