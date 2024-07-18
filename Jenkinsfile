pipeline{
    agent any
    stages{
        stage ('Build'){
            steps{
                echo 'COMPILE'
                sh 'javac Main.java'
            }
        }
        stage ('Run'){
            steps{
                echo'Running'
                sh 'java Main'
            }
        }
    }
}