pipeline {
   
    agent any

    stages {
        stage ('Get Code') {
            steps {
                checkout scm   
            }
        }

        stage ('Build') {
            steps {
                echo 'Build starting'
                sh 'cd lab-app'
                sh 'mvn -f lab-app/pom.xml -Dmaven.test.failure.ignore=true install'
                
                junit 'lab-app/target/surefire-reports/**/*.xml'
                echo 'Build ended'
            }
          }

        stage ('Deployment') {        
            steps {
                echo 'Deployment starting'
                
                echo 'Deployment ended'
            }
        }
    }
}
