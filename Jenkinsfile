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
    post {
        always {
            // Actions to always run, such as cleaning up
            echo 'Cleaning up...'
        }
        success {
            // Actions to run on successful build
            echo 'Build succeeded!'
            emailext(
                subject: 'Jenkins Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}',
                body: '''<p>Build succeeded!</p>
                         <p>Job: ${env.JOB_NAME}</p>
                         <p>Build Number: ${env.BUILD_NUMBER}</p>
                         <p>Build URL: ${env.BUILD_URL}</p>''',
                recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']]
            )
        }
        failure {
            // Actions to run on failed build
            echo 'Build failed!'
            emailext(
                subject: 'Jenkins Build Failure: ${env.JOB_NAME} #${env.BUILD_NUMBER}',
                body: '''<p>Build failed!</p>
                         <p>Job: ${env.JOB_NAME}</p>
                         <p>Build Number: ${env.BUILD_NUMBER}</p>
                         <p>Build URL: ${env.BUILD_URL}</p>''',
                recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']]
            )
        }
    }
}