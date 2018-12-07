pipeline {
    agent any

    stages {
        stage ('Build') {

            steps {
             echo 'Building..'
                }
            }
        
        stage ('Example') {

            steps {
             echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                }
            }

        stage ('Test') {

            steps {
             sh 'make check'
                }
            }
        
        post {
        always {
            junit '**/target/*.xml'
        }
        failure {
            mail to: team@example.com, subject: 'The Pipeline failed :('
        }
    }

        stage ('Deploy') {

            steps {
             echo 'Deploying....'
            }
        }
    }
}