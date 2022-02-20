echo "these comments from GITHUB repo"
pipeline {
    agent any

    stages {
        stage('DEVELOPMENT OR DEV') {
            steps {
                echo 'Building..'
            }
        }
        stage('TESTING OR SIT') {
            steps {
                echo 'Testing EXECUTED FROM GITHUB REPOSITORY'
            }
        }
        stage('Deployment OR PRO') {
            when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                echo 'Deploying....'
                echo "SUCCESS"
            }
        }
    }
}
