pipeline {

    agent any
    tools {
        nodejs "NodeJs"
    }

    stages {

        stage('GitHub') {
            steps {
                git credentialsId: 'jenkins-git-dind', url: 'https://github.com/Joel-glitch-alt/Pipelines-SonarQube-Jenkins.git'
            }
        }
        stage('Unit Test') {
            steps {
                sh 'npm test'
                sh 'npm install'
            }
        }
    }
}


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
//                 sh 'npm test'
//             }
//         }
//     }
// }
