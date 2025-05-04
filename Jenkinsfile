pipeline {
    agent { 
        node {
            label 'docker-agent-alpine'
        }
    }
    triggers {
        pollSCM '*/5 * * * *'
    }
    environment {
        STUDENT_NAME = "Vedha Mudhana"
        ROLL_NO = "SE22UCSE286" // Replace with your actual roll number
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                echo "${env.STUDENT_NAME} ${env.ROLL_NO}"
                sh '''
                echo "Building from Jenkins file"
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                echo "${env.STUDENT_NAME} ${env.ROLL_NO}"
                sh '''
                echo "Testing the build triggered from Jenkins file."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                echo "${env.STUDENT_NAME} ${env.ROLL_NO}"
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
    post {
        always {
            echo "Job triggered by: ${currentBuild.getBuildCauses()[0].userName ?: 'Automated or Timer Trigger'}"
        }
    }
}
