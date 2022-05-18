pipeline {
	agent  any
	// agent { docker { image 'maven:3.6.3'} }

    environment{
        dockerHome= tool 'Mydocker'
		mavenHome= tool 'MyMaven'
        nodeHome= tool 'MyNode'
        PATH="$dockerHome/bin:$nodeHome/bin:$mavenHome/bin:$PATH"
    }
	stages{
		stage('Checkout') {
			steps{
				bat "mvn --version"
				bat 'node --version' // script shell
                bat 'docker version'
				echo "Build"
                echo "$PATH"
                echo "BUILDER_NUMBER -$env.BUILD_NUMBER"
                echo "BUILDER_ID -$env.BUILD_ID"
                echo "BUILDER_TAG -$env.BUILD_TAG"
                echo "JOB_NAME -$env.jOB_NAME"
                echo "BUILDER_URL -$env.BUILD_URL"

			}
		}
		stage('Build'){
			steps{
				bat 'mvn clean compile'
			}
		}
		stage('Test'){
			steps{
				bat 'mvn test'
			}
		}
		stage("Test d'intégration"){
			steps{
				bat 'mvn failsafe:integration-test failsafe:verify '
			}
		}
	}
	post{
		always{
			echo "Je suis genial. Je fonctionne toujours!"
		}
		success{
			echo "Je fonctionne quant tu reussi!"
		}
		failure {
			echo "Je Suis là quand tu echoue!"
		}
	}
}

// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             agent {
//                 docker {
//                     image 'gradle:6.7-jdk11'
//                     // Run the container on the node specified at the
//                     // top-level of the Pipeline, in the same workspace,
//                     // rather than on a new node entirely:
//                     reuseNode true
//                 }
//             }
//             steps {
//                 sh 'gradle --version'
//             }
//         }
//     }
// }
