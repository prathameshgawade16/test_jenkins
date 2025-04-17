pipeline {
    agent any

    parameters {
        gitParameter(
            branchFilter: 'origin/(.*)', 
            defaultValue: 'dev', 
            name: 'Branch', 
            type: 'PT_BRANCH'
        )
    }

    triggers {
        pollSCM('H/10 * * * *')
        
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM', 
                          branches: [[name: "${params.MOBILE_APP_BACKEND_BRANCH}"]],
                          doGenerateSubmoduleConfigurations: false,
                          extensions: [],
                          submoduleCfg: [],
                          userRemoteConfigs: [[url: 'https://your-repository-url.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deploy steps here
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
        }
    }
}
