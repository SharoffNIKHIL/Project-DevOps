pipeline {
    agent { label 'Jenkins-Worker' }
    tools {
        jdk 'java'
        maven 'Maven3'
    }
    stages {
        stage ("Cleanup Workspace") {
            steps {
                script {
                    // Clean up the workspace
                    sh 'rm -rf *'
                }
            }
        }

        stage ("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/SharoffNIKHIL/Project-DevOps.git'
            }
        }

        stage ("Build the Application") {
            steps {
                sh "mvn clean package"
            }
        }

        stage ("Testing the Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
