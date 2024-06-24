pipeline {
    agent { label 'Jenkins-Worker' }
    tools {
        jdk 'java'
        maven 'Maven3'
    }
    stages {
        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/SharoffNIKHIL/Project-DevOps.git'
            }
        }

        stage("Cleanup Workspace") {
            steps {
                script {
                    sh 'ls -la' // List files before cleanup for debugging
                    sh 'rm -rf *'
                    sh 'ls -la' // List files after cleanup for debugging
                }
            }
        }

        stage("Re-Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/SharoffNIKHIL/Project-DevOps.git'
            }
        }

        stage("Build the Application") {
            steps {
                sh 'mvn clean package'
            }
        }

        stage("Testing the Application") {
            steps {
                sh 'mvn test'
            }
        }
    }
}
