def remote = [:]
remote.name = "node-1"
remote.host = "18.218.57.2543"
remote.allowAnyHosts = true

node {
    withCredentials([sshUserPrivateKey(credentialsId: 'jkonfig', keyFileVariable: 'jkonfig', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.identityFile = identity
        stage("SSH Steps Rocks!") {
            writeFile file: 'abc.sh', text: 'ls'
            sshCommand remote: remote, command: 'for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done'
            sshPut remote: remote, from: 'abc.sh', into: '.'
            sshGet remote: remote, from: 'abc.sh', into: 'bac.sh', override: true
            sshScript remote: remote, script: 'abc.sh'
            sshRemove remote: remote, path: 'abc.sh'
        }
    }
}





// def remote = [:]
// // withCredentials([usernamePassword(credentialsId: 'instance', passwordVariable: 'Password', usernameVariable: 'User')]) {
// //     // some block
	
// // }
// // , passwordVariable: 'password'

// // , keyFileVariable: 'Private Key', usernameVariable: 'Username'
// node{
// withCredentials([sshUserPrivateKey(credentialsId: 'jkonfig')]) {

//     // some block
// 	remote.name = 'root'
// 	remote.host = '18.218.57.254'
// 	remote.user = 'ec2-user'
// // 	remote.identityFile = 'Private Key'
// // 	remote.password = '${password}'
// 	remote.allowAnyHosts = true
// }			
// }

	
// pipeline{
// 	agent any
// 		environment{
// 			PATH="/root/lokii:$PATH"
// 		}
// 	parameters{
// 		string defaultValue: 'ContainerNameDefault', description: 'Container name which should be given to Docker container', name: 'ContainerName'
// 		string defaultValue: 'ubuntu', description: 'Image to pull from Docker Hub ', name: 'ImageName'
// 		}
	
// 	stages{		
// //         	stage("git-checkout"){
// // 			steps{
// //                 		git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
// //             		}
// //         	}
// 		stage('Remote SSH') {
// 			steps{
// 	    			sshCommand remote: remote, command: "whoami"
// 	    			sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
// 			}
// 		}
		
// // 	 	stage ("deployment") {
// // 			steps {
// // 				sh '''
// //                 if [ ! "$(docker ps -q -f name=${ContainerName})" ]; then
// // 	                docker run --detach --restart unless-stopped --name ${ContainerName} --env "VIRTUAL_HOST=${ContainerName}" --env "LETSENCRYPT_HOST=${ContainerName}" ${ImageName}
// // 	                if [ ! "$(docker inspect -f {{.State.Running}} ${ContainerName})" ]; then
// // 	                	exit 1	
// // 	                fi
// // 	                docker ps -a
// //                  else
// //                     docker stop ${ContainerName}
// //                     docker rm ${ContainerName}
// //                     docker rmi ${ImageName}
// //                     docker run --detach --restart unless-stopped --name ${ContainerName} --env "VIRTUAL_HOST=${ContainerName}" --env "LETSENCRYPT_HOST=${ContainerName}" ${ImageName}
// // 	                 if [ ! "$(docker inspect -f {{.State.Running}} ${ContainerName})" ]; then
// // 		                exit 1	
// // 	                 fi
// // 	                 docker ps -a
// //                 fi
// // 				'''
// // 			}
// // 		}
//          }
//     }

