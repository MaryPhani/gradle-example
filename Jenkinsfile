pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                echo 'Cloning the Git repository...'
                git url: 'https://github.com/MaryPhani/gradle-example.git'
            }
        }

        stage('Snyk Test') {
            steps {
                echo 'Snyk Testing...'
                script {
                    // Adjusted the credential ID to 'snyk_org_token'
                    snykSecurity (
                        projectName: 'eposhybrid23', 
                        snykInstallation: 'snyk_security', 
                        snykTokenId: 'SNYK-TOKEN',
                        failOnIssues: false
                    )
                }
            }
        }
    }
}
