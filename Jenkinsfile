pipeline {
    agent any

    environment {
        EMAIL_RECIPIENTS = 'venkat26072003@gmail.com'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Your build steps here
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing...'
                // Your test steps here
            }
        }
    }

    post {
        success {
            emailext(
                subject: "SUCCESS: Build #${BUILD_NUMBER} - ${JOB_NAME}",
                body: "Build ${BUILD_NUMBER} of project ${JOB_NAME} was successful.\n\nCheck the build details at ${BUILD_URL}",
                to: "${EMAIL_RECIPIENTS}"
            )
        }
        failure {
            emailext(
                subject: "FAILURE: Build #${BUILD_NUMBER} - ${JOB_NAME}",
                body: "Build ${BUILD_NUMBER} of project ${JOB_NAME} failed.\n\nCheck the build details at ${BUILD_URL}",
                to: "${EMAIL_RECIPIENTS}"
            )
        }
        unstable {
            emailext(
                subject: "UNSTABLE: Build #${BUILD_NUMBER} - ${JOB_NAME}",
                body: "Build ${BUILD_NUMBER} of project ${JOB_NAME} is unstable.\n\nCheck the build details at ${BUILD_URL}",
                to: "${EMAIL_RECIPIENTS}"
            )
        }
    }
}
