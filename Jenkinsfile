pipeline {
	agent {
		node {
			label ('172.31.1.181)
		}
	}
	stages {
		stage ('git_clone'){
			steps {
				sh "cd /mnt/App_Dir"
				sh "rm -rf *"
				sh "git clone https://github.com/rohitkarad24/Container_Deploy.git /mnt/App_Dir"
			}
		}
		stage ('remove container') {
			steps {
				sh"sudo docker system prune -a -f"
			}
		}
		stage ('Q1'){
			steps {
				sh "cd /mnt/Docker_Dir"
				sh "sudo docker run -itdp 80:80 --name rohit httpd"
				sh "sudo docker cp /mnt/App_Dir/Container_Deploy/index.html rohit:/usr/local/apache2/htdocs/"
			}
		}
	}
}
