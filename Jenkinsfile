pipeline {
    agent any

    tools{
        maven "Maven_Home"
    }
    
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/PreethigaH/Springboot-simpleApp'
            }
        }
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
        failure{
            echo "Jenkins build failed"
        }
    }
}
