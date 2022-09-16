pipeline{
    agent any
        environment{
        PATH_JENKINS="/root/lokii:$PATHH"
       }
    stages{
        stage("git-checkout"){
            steps{
                    echo 'Hello Worldssdsad'
              git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
            }
        }
        
        
         stage("Deploy"){
           steps {
				sh """
                if [ ! "$(docker ps -q -f name=${NAME})" ]; then
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
                            """
			}
         }
        
        
        
        
        
        
        
        
        
        
        
        
        
//         stage("A"){
//             steps{
//                 echo "========executing A========"
//                  sh "apt update"
//                 sh "apt install maven"
//                  sh "mv clean pakage"
//             }
    //         post{
    //             always{
    //                 echo "========always========"
    //             }
    //             success{
    //                 echo "========A executed successfully========"
    //             }
    //             failure{
    //                 echo "========A execution failed========"
    //             }
    //         }
    //     }
    // }
    // post{
    //     always{
    //         echo "========always========"
    //     }
    //     success{
    //         echo "========pipeline executed successfully ========"
    //     }
    //     failure{
    //         echo "========pipeline execution failed========"
    //     }
    }
    }
}
