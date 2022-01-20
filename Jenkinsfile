pipeline {

        agent {
           label 'jenkins-slave'
		    options { skipDefaultCheckout() } 
        }
 
    stages {
        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/arunmadan1991/Module3.git']]
                ])
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
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
