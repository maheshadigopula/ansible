pipeline {
    agent any 
    environment {                                       // Declaring at pipeline will allow all the stages to access this variable
        SSH_CRED = credentials('SSH_CRED') 
    }
    stages {
        stage('Lint Checks') {
            when { branch pattern: "feature-.*", comparator: "REGEXP" }
            steps {
                sh "env"
                sh "echo runs only on feature branch"
                sh "echo lint cheks are completed."
            }
        }  

        stage('Performing a Dry-Run') {                 // Just for demo purpose we have hardcoded env and component; That can still be parameterised.
            when { branch pattern: "PR-.*", comparator: "REGEXP"}
            steps {
                sh "env"
                sh "Runs only aginst a PR"
                //sh "ansible-playbook robot-dryrun.yml -e component=frontend -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e ENV=dev"
            }
<<<<<<< HEAD

=======
>>>>>>> 1590fd136a0e33c2c65cbe388dc3da6b8e1f1b30
        }

        stage('Runs against Main') {
            when { branch 'main' }
            steps {
                sh "env"
                sh "echo Main Branch"
            }
        }

<<<<<<< HEAD
        stage('Runs against Tag') {
            when { expression { env.TAG_NAME != null } }                       // TAG_NAME is an env
=======

        stage('Runs against Tag') {
            when { expression { env.TAG_NAME != null } }                       // TAG_NAME is an environmen
>>>>>>> 1590fd136a0e33c2c65cbe388dc3da6b8e1f1b30
            steps {
                sh "env"
                sh "echo $TAG_NAME"
            }
        }
<<<<<<< HEAD
=======
        // stage('Runs against Tag') {
        //     when { expression { env.TAG_NAME != null } }                       // TAG_NAME is an environment
        //     steps {
        //         sh "env"
        //         sh "echo $TAG_NAME"
        //     }
        // }

>>>>>>> 1590fd136a0e33c2c65cbe388dc3da6b8e1f1b30
    }
}

// Pushing changes to feature branch