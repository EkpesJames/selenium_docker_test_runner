pipeline{
	agent any 
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d selenium-hub chrome firefox --scale firefox=4"
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