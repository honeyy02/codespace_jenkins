pipeline {
    agent any
        stages{
            stage('Build'){
                echo "Building...."
                sh 'javac Main.java'
            }
            stage('Run'){
                echo "Running"
                sh 'java Main'
            }
        }
    
}