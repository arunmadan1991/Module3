pipeline {

    agent {
        any {
            image 'maven:3.8.1-adoptopenjdk-11' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '16', 
                    numToKeepStr: '10'
            )
    }
 
    stages {
        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/master']], 
                    userRemoteConfigs: [[url: 'https://github.com/narendrakumar02/AQTPracticeData.git']]
                ])
            }
        }
        stage ('Build') {
            steps {
                bat 'mvn clean package'
           }
        }
        stage(' Unit Testing') {
            steps { 
                echo "Running Unit Tests"
                """
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Running Code Analysis"
                """
            }
        }

        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                sh """
                echo "Building Artifact"
                """

                sh """
                echo "Deploying Code"
                """
            }
        }

    }   
}
