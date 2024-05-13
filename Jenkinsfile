pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/aneez004/flask-hello-world.git'
            }
        }

      
        stage('Deploy to OpenShift') {
            steps {
                script {
                    openshift.withCluster() {
                        openshift.withProject('aneez004-dev') {
                            openshift.apply(file: 'app-template.yaml')
                        }
                    }
                }
            }
        }
    }
}
