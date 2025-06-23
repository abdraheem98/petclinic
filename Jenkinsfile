pipeline {
	agent any
    stages {
        stage('Build on k8') {
            steps {
                sh 'pwd'
                sh 'ls -ltr helm'
                sh 'cp -R helm/petclinic .'
                sh 'ls -ltr'
                sh '/usr/local/bin/helm upgrade --install petclinic-app ./petclinic --set image.repository=docker.io/abdraheem98/petclinic'
            }
        }
    }
}
