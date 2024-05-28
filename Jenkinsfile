pipeline {
    agent any

    tools{
        maven "Maven_Home"
    }
    
    stages {
        stage('Compile Code') {
            steps {
                bat "mvn compile"
            }
        }
        stage('Test Code') {
            steps {
                bat "mvn test"
            }
        }
        stage('Create build') {
            steps {
                bat "mvn package"
            }
        }
    }

    post{
        success{
            echo "Jenkins build - successful"
            emailext body: 'Successfully completed the build', subject: 'Pipeline Status', to: 'pmuralidharan@teksystems.com'
        }
        failure{
            echo "Jenkins build failed"
            emailext body: 'Failed to complete the build', subject: 'Pipeline Status', to: 'pmuralidharan@teksystems.com'
        }
    }
}
