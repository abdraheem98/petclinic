pipeline {
    agent any

    environment {
        // Set your kubeconfig path here (adjust if different)
        KUBECONFIG = "/home/ubuntu/.kube/config"
    }

    stages {
        stage('Build and Deploy on K8s') {
            steps {
                script {
                    def imageTag = "${env.BUILD_NUMBER}"
                    sh """
                        echo 'Current directory:'
                        pwd

                        echo 'Copying Helm chart files...'
                        cp -R helm/* .

                        echo 'Listing directory contents...'
                        ls -ltr

                        echo 'Deploying via Helm...'
                        /usr/local/bin/helm upgrade --install petclinic-app petclinic \
                          --set image.repository=docker.io/abdraheem98/petclinic \
                          --set image.tag=${imageTag}
                    """
                }
            }
        }
    }
}
