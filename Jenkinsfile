pipeline{
	agent any
		stages{
			stage('build'){
				steps{
					sh"docker build -t banik123/argocd-demo:${env.GIT_COMMIT} ."
					sh "docker login --username banik123 --password Kp@43#qc && docker push alexmt/argocd-demo:${env.GIT_COMMIT}""
				}
			}
		}
	}

