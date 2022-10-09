pipeline {
	agent {
		node {
			label ('Docker_Host')
		}
	}
	stages {
	stage (git_clone){
			steps {
				sh "cd /mnt/App_Dir"
				sh "rm -rf *"
				sh "git clone https://github.com/rohitkarad24/Container_Deploy.git"
			}
		}
		stage (Q1){
			steps {
				sh "cd /mnt/Docker_Dir"
				sh "sudo docker run -itdp 80:80 httpd"
				sh "cp /mnt/App_Dir/index.html /usr/local/apache2/htdocs"
			}
		}
	}
}
