pipeline {
	agent any
			
	stages {
		stage('Clean workspace'){
			steps{
				script{
					sh 'rm -rf $PWD/final_project'						
				}
			}
		}
			
		stage('Cloning Repo'){
			steps {
				script{
					sh 'git pull https://github.com/kenneth-cruz/final_project.git' 
				}		
			}
		}
   				
		stage('Deployment'){
			steps{
				script{
  					sh '/usr/local/bin/ansible-playbook playbook.yaml'
				}
  			}
		}
						
		stage('Testing'){
				steps{
					ansiblePlaybook disableHostKeyChecking: true, playbook: 'playbook.yaml'
				}				
		}
	}
}