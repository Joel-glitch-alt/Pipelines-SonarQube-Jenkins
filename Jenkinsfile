
// pipeline {
//     agent any
//     tools {
//         nodejs "NodeJs"
//     }

//     stages {
//         stage('GitHub') {
//             steps {
//                 git credentialsId: 'jenkins-git-dind', url: 'https://github.com/Joel-glitch-alt/Pipelines-SonarQube-Jenkins.git'
//             }
//         }

//         stage('Install Dependencies') {
//             steps {
//                 sh 'npm install'
//             }
//         }

//         stage('Unit Test') {
//             steps {
//                 sh 'npm install'
//                 sh 'chmod +x ./node_modules/.bin/jest'
//                 sh 'npx jest --passWithNoTests'
//             }
//         }
//     }
// }

pipeline {
    agent any
    tools {
        nodejs "NodeJs"
    }

    environment {
        // Name must match the configured SonarQube instance in Jenkins
        SONARQUBE_ENV = 'SonarQube'
    }

    stages {
        stage('GitHub') {
            steps {
                git credentialsId: 'jenkins-git-dind', url: 'https://github.com/Joel-glitch-alt/Pipelines-SonarQube-Jenkins.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Unit Test') {
            steps {
                sh 'npm install'
                 sh 'chmod +x ./node_modules/.bin/jest'
                 sh 'npx jest --passWithNoTests'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv("${SONARQUBE_ENV}") {
                    sh 'sonar-scanner'
                }
            }
        }
    }
}


