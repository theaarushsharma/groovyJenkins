pipeline{
    agent any
    environment{
        NODE_ENV = 'lab4'
    }
    stages{
        
        stage('install'){
            steps{
                bat 'npm install'
            }
        }
        stage('run'){
            steps{
                bat 'npx wdio run wdio.conf.js'
            }
        }
        stage('Import results to Xray') {
            steps {
                step([$class: 'XrayImportBuilder', endpointName: '/junit', importFilePath: 'C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/workspace/jiraXray/report/*.xml', importToSameExecution: 'true', projectKey: 'IN', serverInstance: '58e0dd80-f4a7-4a05-a650-2f1cfd33444e'])
            }
        }
    }
}
