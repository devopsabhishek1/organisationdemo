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
					sh"git clone https://github.com/abhishekmha/gitopsdemo.git"
					sh "git config --global user.email 'abhishekmhaskar55@gmail.com'"
					
					dir("gitopsdemo"){
						sh "cd ./e2e && kustomize edit set image banik123/argocd-demo:${env.GIT_COMMIT}"
						sh "git commit -am 'Publish new version' && git push || echo 'no changes'"
					}
				}
			}
		}
	}

