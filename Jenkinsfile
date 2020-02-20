pipeline{
	agent any{
		stages{
			stage('build'){
				steps{
					sh"docker build -t banik123/argocd-demo:${env.GIT_COMMIT} ."
				}
			}
		}
	}
}
