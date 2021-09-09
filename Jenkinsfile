pipeline {
    agent any
    environment {
        registryCredential = 'dockerhub'
    }
    stages {
        stage('Build') {
            steps {
                    sh 'docker build -t backend .'
                    sh 'docker tag backend mohsinm/backend:third'
            }
        }
        // stage('Test') {
        //     steps {
        //         sh 'docker container rm -f node || true'
        //         sh 'docker container run -p 8081:8080 --name backend node -d mohsinm/backend'
        //         sh 'docker container run -p 8082:8080 --name frontend -d mohsinm/frontend'
        //         sh 'curl -I http://localhost:8082'
        //     }
        // }
        stage('Publish') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                        sh 'docker push mohsinm/backend:third'
                    }
                }
            }
        }
    }
}
