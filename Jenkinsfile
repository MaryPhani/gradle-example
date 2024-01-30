pipeline {
    agent any
    
    stages {
        stage('Snyk Test') {
            steps {
                echo 'Snyk Testing...'
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
