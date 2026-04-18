pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Fourat-Ben-Ali/TimeSheet.git'
            }
        }

        stage('COMPILATION') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar'
            }
        }
    }
}
