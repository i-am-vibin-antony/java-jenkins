pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // Get some code from a GitHub repository
                git url: 'https://github.com/jglick/simple-maven-project-with-tests.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven on a Unix agent
                sh 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}

