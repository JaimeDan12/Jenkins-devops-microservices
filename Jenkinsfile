pipeline {
	// agent  any
	agent { 
		docker { 
		image 'maven:3.8.5'
		} 
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version' // script shell
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
