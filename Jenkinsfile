pipeline {

        agent {
           label 'agent1'
        }
 
    stages {
        stage ('Build') {
            steps {
                bat 'mvn clean package'
           }
        }
        stage(' Unit Testing') {
            steps { 
                echo "Running Unit Tests"
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Running Code Analysis"
  
            }
        }

        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                echo "Building Artifact"
                echo "Deploying Code"

            }
        }
    }   
}
