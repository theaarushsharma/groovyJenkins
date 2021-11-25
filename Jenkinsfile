pipeline{
    agent any
    stages{
        stage('install'){
            steps{
                bat 'npm install'
            }
        }
        stage('run'){
            steps{
                bat 'npx wdio'
            }
        }
        stage('Import results to Xray') {
            steps {
                step([$class: 'XrayImportBuilder', endpointName: '/junit', importFilePath: 'C:\Users\aarus\Documents\wbdrPrg\report\*.xml', importToSameExecution: 'true', projectKey: 'IN', serverInstance: '58e0dd80-f4a7-4a05-a650-2f1cfd33444e'])
            }
        }
    }
}