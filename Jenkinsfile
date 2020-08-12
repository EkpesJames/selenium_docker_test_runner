pipeline{
	agent any 
	stages{
		stage("Pull Latest Image"){
			steps{
				sh "docker pull gridtest/selenium-dockertest:testWorks"
			}
		}		
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d selenium-hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up search-module"
			}
		}		
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}		
}