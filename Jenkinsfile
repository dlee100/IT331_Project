pipeline {
    agent any

    options {
        buildDiscarder(logRotator(numToKeepStr:'5'))
        disableConcurrentBuilds()
    }

    environment {
        PROJECT = "IT331"
        DOCKER_ORG = "application"
    }

    stages {
        stage('checkout') { steps { checkout scm } }

        stage('code lint') {
            steps {
                script {
                    sh 'echo TODO'
                }
            }
        }

        stage('docker build') {
            steps {
                script {
                    sh '''
                    docker ps
                    '''

                    stage('Docker Build') {
                       customImage = docker.build("$DOCKER_ORG/${PROJECT}", "-f Dockerfile .")
                       println("Built image ${customImage.imageName()}")
                    }
                }
            }
        }

        stage('Clean Up') {
            steps {
                script {
                    println('todo')
                }
            }
        }


    }
}

