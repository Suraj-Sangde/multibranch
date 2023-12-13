pipeline{
		agent {
			label{
					label "built-in"
					customWorkspace "/mnt/customWorkspace23"
				}
			}
		
		stages{
		     stage ("install-httpd"){
					agent{
						label{
								label "slave-1"
								customWorkspace "/mnt/workingarea"
						steps{
							sh "sudo yum install httpd -y"
							sh " sudo service httpd restart"
							sh "sudo chmod -R 777 /mnt"
							}
							}
			stage ("deploy-httpd") {
						steps{
								sh "sudo rm -rf *"
								sh "sudo scp -i /mnt/ohio.pem /mnt/scm/index.html 172.31.27.223@ec2-user:/mnt"
								sh "sudo chmod -R 777 /var/www/html"
							}
						}	
					}
				}
