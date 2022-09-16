pipeline{
    agent any
       environment{
        PATH="/root/lokii:$PATH"
       }
      parameters{
          string defaultValue: 'jenkins', description: 'asdkkjfas', name: 'name'
       }
    stages{
         stage("git-checkout"){
            steps{
                    
                
              git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
                echo"Hello Worldssdsad"
            }
        }
          stage("d"){
              steps{
            echo "hi ${name},ahdfajdf"
		      sh "printenv"
		      sh "ls"
              }
        }
	    
	 stage ("Pulling Config") {
			steps {
				sh '''
                if [ ! "$(docker ps -q -f name=9toys.com)" ]; then
	                docker run --detach --restart unless-stopped --name 9toys.com --env "VIRTUAL_HOST=9toys.com" --env "LETSENCRYPT_HOST=9toys.com" 9930i/9toys_ng:prod
	                if [ ! "$(docker inspect -f {{.State.Running}} 9toys.com)" ]; then
	                	exit 1	
	                fi
	                docker ps -a
                 else
                    docker stop 9toys.com
                    docker rm 9toys.com
                    docker rmi 9930i/9toys_ng:prod
                    docker run --detach --restart unless-stopped --name 9toys.com --env "VIRTUAL_HOST=9toys.com" --env "LETSENCRYPT_HOST=9toys.com" 9930i/9toys_ng:prod
	                 if [ ! "$(docker inspect -f {{.State.Running}} 9toys.com)" ]; then
		                exit 1	
	                 fi
	                 docker ps -a
                fi
				'''
			}
		}
         }
    }
