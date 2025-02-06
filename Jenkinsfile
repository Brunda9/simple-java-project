pipeline {
    agent any
  
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
    
    
    //     stage('Build') {
    //         steps {
    //     sh 'npm install'
    //   }
    // }

}
}
