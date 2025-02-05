pipeline {
    agent any

    stages {
        stage('Workspace cleanup') {
            steps {
                cleanWs()  // Clean up the workspace before starting the build
            }
        }
        
        stage('Clone') {
            steps {
                checkout scmGit(
                    branches: [[name: '*/master']],
                    browser: github('https://github.com/Brunda9/simple-java-project.git'),
                    extensions: [],
                    userRemoteConfigs: [[credentialsId: 'test_git', url: 'https://github.com/Brunda9/simple-java-project']]
                )
            }
        }

        stage('Build') {
            steps {
                // Assuming Maven is installed and available on the Jenkins machine
                sh 'mvn clean install'  // Clean and install the project dependencies
            }
        }

        stage('Test') {
            steps {
                // Run tests (Maven will run tests by default if they're configured)
                sh 'mvn test'  // Execute tests after building
            }
        }

        stage('Deploy') {
            steps {
                // If you have a deploy stage, you can add the logic here
                echo 'Deploying project...'  // Placeholder for deploy logic
            }
        }
    }
}
