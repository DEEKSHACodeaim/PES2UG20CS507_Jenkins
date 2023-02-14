pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                sh 'g++ -o PES2UG20CS507_1 PES2UG20CS507_1.cpp'
                sh 'echo "PES2UG20CS507-1"'
            }
        }
        stage('Test'){
            steps{
                
                sh './PES2UG20CS507_1'
            }
            }
        }
        
    }
    post{
        failure{
            echo 'Pipeline failed'
        }
    }
}
