pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/your/repo.git'
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
