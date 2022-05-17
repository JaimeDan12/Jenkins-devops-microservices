// pipeline {
// 	agent  any
// 	agent { docker { image 'maven:3.6.3'} }
// 	stages{
// 		stage('Build') {
// 			steps{
// 				sh 'mvn --version' // script shell
// 				echo "Build"
// 			}
// 		}
// 		stage('Test'){
// 			steps{
// 				echo "Test "
// 			}
// 		}
// 		stage("Test d'intégration"){
// 			steps{
// 				echo "Test d'integration"
// 			}
// 		}
// 	}
// 	post{
// 		always{
// 			echo "Je suis genial. Je fonctionne toujours!"
// 		}
// 		success{
// 			echo "Je fonctionne quant tu reussi!"
// 		}
// 		failure {
// 			echo "Je Suis là quand tu echoue!"
// 		}
// 	}
// }

pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'gradle:6.7-jdk11'
                    // Run the container on the node specified at the
                    // top-level of the Pipeline, in the same workspace,
                    // rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh 'gradle --version'
            }
        }
    }
}
