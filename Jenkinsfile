pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                git url: 'https://github.com/nlmz94/TP1-DevOps-GIT', branch: 'main'
            }
        }
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('docker-build') {
            steps {
                bat 'docker build -t naelmez/tp7:1.0 .'
            }
        }
        stage('docker-push') {
            steps {
                bat 'docker login -u naelmez -p temporarypassword'
                bat 'docker push naelmez/tp7:1.0'
            }
        }
    }
    post {
        failure {
            emailext body: 'Ce Build $BUILD_NUMBER a échoué',
            recipientProviders:[requestor()], subject: 'build', to: 'nmz94140@gmail.com'
        }
    }
}
