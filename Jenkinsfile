pipeline {
    agent any
    stages {
        stage('Build and Deploy on K8s') {
            steps {           
                sh 'pwd'
                sh 'cp -R helm/* .'
                sh 'ls -ltr'
                script {
                    def imageTag = "${env.BUILD_NUMBER}"
                    sh "/usr/local/bin/helm upgrade --install petclinic-app petclinic \
                        --set image.repository=docker.io/abdraheem98/petclinic \
                        --set image.tag=${imageTag}"
                }
            }
        }
    }
}
