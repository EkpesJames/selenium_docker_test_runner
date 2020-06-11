pipeline{
	agent any 
	stages{		
		stage("Ren Test"){
			steps{
				bat "docker-compose up"
			}
		}
		stage("Bring Grid Down"){
			steps{
				bat "docker-compose down"
			}
		}		
	}		
}