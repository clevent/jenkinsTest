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
                newman run Swagger_Petstore.postman_collection.json -e Generate_JWT.postman_environment.json -r cli,htmlextra -- reporter -htmlextra -export 1234.html
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
