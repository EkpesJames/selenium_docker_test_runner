pipeline{
	agent any 
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d selenium-hub chrome firefox --no-color"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module"
			}
		}		
		stage("Stop Grid"){
			steps{
				bat "docker-compose down"
			}
		}
	}		
}