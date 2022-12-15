/* groovylint-disable CompileStatic */
pipeline {
    agent any
    environment {
        USERNAME = 'hugosinp'
        FAVORITE_COLOR = 'blue'
    }
    stages {
        stage('git checkout') {
            steps {
                git url: 'https://github.com/nlmz94/TP1-DevOps-GIT', branch: 'main'
            }
        }
        stage('Lister les variables') {
            steps {
                bat 'set'
            }
        }
        stage('Utilisation des variables') {
            steps {
                echo env.USERNAME
                echo env.FAVORITE_COLOR
            }
        }
    }
}
