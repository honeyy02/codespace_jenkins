pipeline{
    agent any
    stages{
        stage ('Build'){
            steps{
                echo "Compiling the code"
                sh 'javac Main.java'
            }
        }
        stage ('Run'){
            steps{
                echo "Running.."
                sh 'java Main'
            }
        }
    }
    
}