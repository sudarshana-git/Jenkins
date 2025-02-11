pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M399" and add it to the path.
        maven "M399"
    }

    stages {
        stage('Echo version') {
            steps {
                sh 'echo Print Maven version'
                sh 'mvn -version'
            }
        }
        
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                // git branch: 'main', url: 'https://github.com/sudarshana-git/Jenkins.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"
            }
        }

        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
