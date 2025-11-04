// This is your new Jenkinsfile
pipeline {
    agent any

    stages {
        stage('1. Git Checkout') {
            steps {
                // Get the code from GitHub
                git 'https://github.com/Abhishek-A2077/JenkinsHomeverse.git' // You can change this to your fork's URL
            }
        }

        stage('2. Deploy to S3') {
            steps {
                // Sync all files to the S3 bucket
                // The IAM Role on the EC2 instance gives it permission
                // The --delete flag removes old files
                sh 'aws s3 sync . s3://abhishek-homeverse-site-91736/ --delete' // <-- This is the corrected line
            }
        }
    }

    post {
        success {
            echo 'Website deployed successfully!'
        }
    }
}