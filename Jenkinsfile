pipeline {
    agent any
    stages {
        stage('Build'){
            steps {
                sh 'g++ -o working working.cpp'
                sh 'echo "PES2UG20CS507-1"'
            }
        }
        stage('Test'){
            steps{
                
                sh './working'
            }
                
            }
        }
        stage('Deploy'){
            steps{
                sh 'git add working'
                sh 'git commit -m "Add compiled program"'
                sh 'git push origin main'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline failed'
        }
    }
}
