pipeline {
    agent {label 'Jenkins-Worker'}
    tools {
        jdk 'java'
        maven 'Maven3'
    }
   stages {
     stage ("Cleanup Workspace"){
        steps {
            script {
                sh 'rm -rf *'
            }
        }
     }

     stage ("Checkoput from SCM") {
        steps {
            git branch: 'main', credentialsId: 'github', url: 'https://github.com/SharoffNIKHIL/Project-DevOps.git'
        }
     }

     stage ("build the application") {
        steps {
            sh "mvn clean package"
        }
     }

     stage ("Testing the application") {
        steps {
            sh "mvn test"
        }
     }
   }
}
