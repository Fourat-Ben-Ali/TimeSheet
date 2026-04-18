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
        }d

        stage('ANALYSIS') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=squ_978bc87eb329f2cb75d0d07136624cb082ab7f50'
            }
        }
    }
}
