pipeline {
    agent any  // Runs on any available agent

    environment {
        // Define any global environment variables here, if needed
        MY_ENV_VAR = 'value'  // Example: Replace with actual environment variable
    }

    stages {
        // Stage 1: Checkout code from the Git repository
        stage('Checkout Code') {
            steps {
                // Pull the latest code from the Git repository
                git 'https://github.com/srinitha062/team3_casestudy.git'
            }
        }

        // Stage 2: Build the project
        stage('Build') {
            steps {
                script {
                    // Build commands (for example, using Maven)
                    echo 'Building the project...'
                    // Replace with actual build command (e.g., `mvn clean install`)
                    sh 'mvn clean install'
                }
            }
        }

        // Stage 3: Run tests
        stage('Test') {
            steps {
                script {
                    // Test commands (e.g., running unit tests)
                    echo 'Running tests...'
                    // Replace with actual test command (e.g., `mvn test` for Maven)
                    sh 'mvn test'
                }
            }
        }

        // Stage 4: Deploy the application
        stage('Deploy') {
            steps {
                script {
                    // Deployment commands (e.g., deploy to a server or cloud service)
                    echo 'Deploying the application...'
                    // Replace with actual deploy command (e.g., deploy.sh or deployment command)
                    sh './deploy.sh'  // Example: Running a deployment script
                }
            }
        }
    }

    post {
        success {
            // Actions to take on successful build (e.g., notify team)
            echo 'Build was successful!'
            // Example: send email or Slack notification
            // mail to: 'team@example.com', subject: 'Build Successful', body: 'The build succeeded.'
        }
        failure {
            // Actions to take on failed build (e.g., notify team or log issue)
            echo 'Build failed.'
            // Example: send email or Slack notification on failure
            // mail to: 'team@example.com', subject: 'Build Failed', body: 'The build failed.'
        }
    }
}
