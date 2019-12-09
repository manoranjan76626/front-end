pipeline {
    agent any

    tools{
       nodejs 'test-nodejs'
    } 
    stages {
        stage('Build') { 
            steps {
            echo 'Building..'
            sh  'npm install'
                // 
            }
        }
        stage('Test') { 
            steps {
                echo 'Testing..'
                sh 'npm test'
                // 
            }
        }
        stage('Package') { 
            steps {
                echo 'Deploying....'
                sh 'npm run package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
                // 
            }
        }
    }
}
