pipeline{
	agent any 
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull gridtest/selenium-dockertest"
			}
		}		
		stage("Convert file"){
			steps{
				bat "dos2unix ./usr/share/dockerSelenium/healthcheck.sh"
			}
		}				
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d selenium-hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module"
			}
		}		
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			bat "docker-compose down"
		}
	}		
}