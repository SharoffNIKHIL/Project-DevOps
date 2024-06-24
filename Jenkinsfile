pipeline {
    agent {label 'Jenkins_worker'}
    tools {
        jdk 'Java21'
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
            git branch: 'main', credentialsId: 'github', url: 'url of the repository'
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