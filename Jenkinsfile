pipeline {
	agent any
			
	stages {
		stage('Clean workspace'){
			steps{
				script{
					sh 'rm -rf $PWD/final_project'
					sh 'git clone https://github.com/kenneth-cruz/final_project.git' 						
				}
			}
		}
		
   				
		stage('Ansible'){
			steps{
                ansiblePlaybook disableHostKeyChecking: true, installation: 'ansible', playbook: 'playbook.yaml'
  			}
		}
						
		stage('Testing'){
				steps{
					script {
						sh 'sleep 10' 
						sh 'kubectl get all --all-namespaces'
					}
				}				
		}
	}
}