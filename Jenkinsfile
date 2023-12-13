pipeline{
		agent {
			label{
					label "built-in " 
					customWorkspace "/mnt/customWorkspace23"
				}
			}
		
		stages{
			stage ("clean-workspace") {
						steps{
							sh "sudo rm -rf *"
						}
						}
		     stage ("install-httpd"){
					agent{
						label{
								label "slave-2"
								customWorkspace "/mnt/workingarea"
						}
					}
						steps{
							sh "sudo yum install httpd -y"
							sh " sudo service httpd restart"
							sh "sudo chmod -R 777 /mnt"
							}
							}
			 stage ("copy-index.html"){
					agent{
						label{
								label "slave-2"
								customWorkspace "/mnt/workingarea"
						}
					}
						steps{
							sh "sudo cp /mnt/workingarea/index.html /var/www/html"
							sh " sudo chmod -R 777 /var/www/html/*"
							}
							}
					}
				}
