pipeline {
	agent  any
	stages{
		stage('Build'){
			steps{
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
				echo "Test d'intégration"
			}
		}
	}
	post{
		always{
			echo "Je suis génial. Je fonctionne toujours!"
		}
		success{
			echo "Je fonctionne quant tu réussi!"
		}
		failure {
			echo "Je fonctionnne quand tu échoue!"
		}
	}

}
