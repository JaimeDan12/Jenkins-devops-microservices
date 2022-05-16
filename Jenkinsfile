pipeline {
	agent {Docker {image: 'maven 3.8.4'}}
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
			echo "Je fonctionnne quand tu échoue!"
		}
	}

}
