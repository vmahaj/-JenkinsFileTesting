pipeline {
    agent any
    stages {
        stage ('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving Artifacts..'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to Staging') {
            Build job: 'Deploy-to-Staging'
        }
    }

}