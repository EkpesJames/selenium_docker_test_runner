pipeline{
	agent any 
	stages{
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module"
			}
		}
		stage("Bring grid down"){
			steps{
				bat "docker-compose down"
			}
		}		
	}		
}