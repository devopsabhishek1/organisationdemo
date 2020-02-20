pipeline{
	agent any
		stages{
			stage('build'){
				steps{
					sh"docker build -t banik123/argocd-demo:${env.GIT_COMMIT} ."
					sh "docker login --username banik123 --password Kp@43#qc && docker push banik123/argocd-demo:${env.GIT_COMMIT}"
				}
			}
			
			stage('deploy e2e'){
				steps{
					sh"git clone https://abhishekmha:abhishek55@@github.com/abhishekmha/gitopsdemo.git"
					sh "git config --global user.email 'abhishekmhaskar55@gmail.com'"
				}
			}
		}
	}

