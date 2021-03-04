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
  					sh '/Library/Frameworks/Python.framework/Versions/3.9/bin/ansible-playbook playbook.yaml'
				}
  			}
		}
						
		stage('Testing'){
				steps{
					script {
						sh 'sleep 10' 
						sh '/usr/local/bin/kubectl get all --all-namespaces'
					}
				}				
		}
	}
}
