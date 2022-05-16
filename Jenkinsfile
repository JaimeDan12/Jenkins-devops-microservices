pipeline {
	// agent  any
	// agent { docker { image 'maven:3.8.5'} }
	agent {
    docker {
        label 'docker'
        image 'python:3.7'
    }
}
	stages{
		stage('Build'){
			steps{
				sh 'py --version' // script shell
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				echo "Test "
			}
		}
		stage("Test d'intégration"){
			steps{
				echo "Test d'integration"
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
