pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/rajusamudram/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t rajusamudram/saleor-dashboar:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push rajusamudram/saleor-dashboar:DEV'
            }
        }
        
    }
}
