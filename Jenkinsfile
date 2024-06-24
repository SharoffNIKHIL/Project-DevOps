pipeline {
    agent {label 'Jenkins_worker'}
    tools {
        jdk 'java21'
        maven 'Maven3'
    }
   stages {
     stage ("Cleanup Workspace"){
        steps {
            cleanWS ()
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
