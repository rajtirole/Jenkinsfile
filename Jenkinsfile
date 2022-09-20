pipeline{
    agent any
       environment{
        PATH="/root/lokii:$PATH"
       }
      parameters{
          string defaultValue: 'ContainerNameDefault', description: 'Container name which should be given to Docker container', name: 'ContainerName'
	  string defaultValue: 'ubuntu', description: 'Image to pull from Docker Hub ', name: 'ImageName'
       }
	
	node {
  def remote = [:]
  remote.name = 'root'
  remote.host = '194.195.115.147'
  remote.user = 'root'
  remote.password = 'OLUYOBxOHwRA'
  remote.allowAnyHosts = true
  stage('Remote SSH') {
    sshCommand remote: remote, command: "ls -lrt"
    sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
  }
}
// 	 remote.name = 'root'
//     remote.host = '194.195.115.147'
//     remote.user = 'root'
//     remote.password = 'OLUYOBxOHwRA'
//     remote.allowAnyHosts = true
//    
	
    stages{
         stage("git-checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
            }
        }
	    
	    
	 stage ("deployment") {
			steps {
				sh '''
                if [ ! "$(docker ps -q -f name=${ContainerName})" ]; then
	                docker run --detach --restart unless-stopped --name ${ContainerName} --env "VIRTUAL_HOST=${ContainerName}" --env "LETSENCRYPT_HOST=${ContainerName}" ${ImageName}
	                if [ ! "$(docker inspect -f {{.State.Running}} ${ContainerName})" ]; then
	                	exit 1	
	                fi
	                docker ps -a
                 else
                    docker stop ${ContainerName}
                    docker rm ${ContainerName}
                    docker rmi ${ImageName}
                    docker run --detach --restart unless-stopped --name ${ContainerName} --env "VIRTUAL_HOST=${ContainerName}" --env "LETSENCRYPT_HOST=${ContainerName}" ${ImageName}
	                 if [ ! "$(docker inspect -f {{.State.Running}} ${ContainerName})" ]; then
		                exit 1	
	                 fi
	                 docker ps -a
                fi
				'''
			}
		}
         }
    }
