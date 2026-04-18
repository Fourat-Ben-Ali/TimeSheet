pipeline {
    agent any

    environment {
        SONAR_TOKEN = credentials('SONAR_TOKEN')
    }

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
        }d

        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=${SONAR_TOKEN}'
            }
        }
    }
}
