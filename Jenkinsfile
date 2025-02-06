pipeline {
    agent any

    tools {
        // Specify the tools you want to use in the pipeline
        maven 'Maven'    // Example for Maven version configured in Jenkins
    }
  
    stages {
        stage('Workspace cleanup') {
            steps {
                cleanWs()
            }
	}
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], browser: github('https://github.com/Brunda9/simple-java-project.git'), extensions: [], userRemoteConfigs: [[credentialsId: 'test_git', url: 'https://github.com/Brunda9/simple-java-project']])
            }
        }
    
         stage('Build') {
             steps {
                 script {
                    // Run the 'mvn install' command in the build step
                     sh 'mvn clean install'  // This command will execute Maven's install phase
                }
            }
        }
'
       }
     }

}
}
