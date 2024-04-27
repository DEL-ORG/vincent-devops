pipeline {
    agent any
    environment {
        DOCKER_HUB_REGISTRY="devopseasylearning"
        DOCKER_CREDENTIAL_ID = 'del-docker-hub-auth'
    }
    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: '')
        string(name: 'IMAGE_TAG', defaultValue: 'latest', description: '')
    }
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    git credentialsId: 's6-jenkins',
                        url: 'https://github.com/DEL-ORG/vincent-devops',
                        branch: "${params.BRANCH_NAME}"
                }
            }
        }
    }
}