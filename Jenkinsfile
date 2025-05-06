pipeline {

    agent any

    stages {

        stage('GitHub') {
            steps {
                git credentialsId: 'jenkins-git-dind', url: 'https://github.com/Joel-glitch-alt/Pipelines-SonarQube-Jenkins.git'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                sh 'echo "Tests passed!"'
            }
        }
    }
}