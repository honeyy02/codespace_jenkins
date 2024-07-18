pipeline{
    agent any
    stages{
        stage('Build'){
            step{
                echo "Compiling the code"
                sh 'javac Main.java'
            }
        }
        stage ('Run'){
            step{
                echo "Running.."
                sh 'java Main'
            }
        }
    }
}