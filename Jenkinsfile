pipeline {
    agent any
    
    stages {
        stage('Snyk Test') {
            steps {
                echo 'Snyk Testing...'
                
                script {
                    def snykToken = credentials('SNYK-TOKEN')  // Use the correct Credential ID

                    if (snykToken == null) {
                        error "Snyk API token with Credential ID 'SNYK-TOKEN' not found."
                    }

                    snykSecurity(
                        projectName: 'eposhybrid23',
                        snykInstallation: 'snyk_security',
                        snykTokenId: snykToken,
                        failOnIssues: false
                    )
                }
            }
        }
    }
    
    post {
        always {
            echo 'This runs always, even on success or failure'
            // Add any cleanup or final steps if needed
        }
    }
}

