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
            mail to: 'venkat26072003@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
    }
}
}
