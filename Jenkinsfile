pipeline {
    agent any
    environment{
        SSH_CREDS = credentials('SSH_CREDS')
    }

    stages{
        stage('performing dry run') {
            steps{
                sh " env "
                sh" ansible-playbook -i inv-dev robot.yml -e component=frontend -e ansible_user=${SSH_CREDS_USR} -e ansible_password=${SSH_CREDS_PSW}"
            }
        }
    }
}    
