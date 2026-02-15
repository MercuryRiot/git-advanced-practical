pipeline {
    agent any
    
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
        timestamps()
    }
    
    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning Git Repository...'
                git url: 'https://github.com/MercuryRiot/git-advanced-practical.git', branch: 'main'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building Project...'
                echo 'Build Status: SUCCESS'
            }
        }
        
        stage('Echo Build Status') {
            steps {
                echo 'Pipeline Build Completed Successfully!'
            }
        }
        
        stage('Archive Artifacts') {
            steps {
                echo 'Archiving Build Artifacts...'
                archiveArtifacts artifacts: '**/*.txt', allowEmptyArchive: true
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution finished.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
