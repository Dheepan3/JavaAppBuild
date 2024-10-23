pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Pull the code from the GitHub repository
                git url: 'https://github.com/Dheepan3/JavaAppBuild.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Use Maven to build the Java application
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run tests after building the application
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Package the Java application (create JAR/WAR)
                sh 'mvn package'
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Archive the build artifacts (JAR or WAR file)
                archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            }
        }
    }
}
