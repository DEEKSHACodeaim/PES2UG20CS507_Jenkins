pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                sh 'mvn clean install'
                g++ working.cpp -o working
                echo 'Build Stage Successful'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
                echo 'Test Stage Successful'
                post{
                    always{
                        junit 'target/surefire-reports/*.xml'
                    }
                }
            }
        }
        stage('Deploy'){
            steps{
                sh 'mvn deploy'
                echo 'Deployment Successful'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline failed'
        }
    }
}
