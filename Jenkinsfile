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
        }
        failure{
            echo "Jenkins build failed"
        }
    }
}
