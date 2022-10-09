pipeline {
	agent {
		node {
			label ('Docker_Host')
		}
	}
	stages {
	stage (git_clone){
			steps {
				sh "cd /mnt/Docker_Dir"
				sh "git clone https://github.com/rohitkarad24/Container_Deploy.git"
			}
		}
		stage (Q1){
			steps {
				sh "cd /mnt/Docker_Dir"
				sh "docker run -p 80:80 httpd"
				sh "cp -r index.html /usr/local/apache2/htdocs"
			}
		}
	}
}
