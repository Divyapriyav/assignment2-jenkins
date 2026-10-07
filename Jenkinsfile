pipeline {

    agent none

    stages {

        stage('Deploy To Test') {

            agent {
                label 'test'
            }

            steps {

                checkout scm

                sh '''
                rm -rf /home/ubuntu/test-app/*
                cp -r * /home/ubuntu/test-app/
                '''

            }
        }

        stage('Deploy To Prod') {

            agent {
                label 'prod'
            }

            steps {

                sh '''
                rm -rf /home/ubuntu/prod-app/*
                cp -r * /home/ubuntu/prod-app/
                '''

            }
        }
    }
}
