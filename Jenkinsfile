pipeline{
    agent any
    stages{   
        stage('Remote SSH') {
            steps{
                script{
                    withCredentials([sshUserPrivateKey(credentialsId: 'jkonfig', keyFileVariable: 'keyFile', usernameVariable: 'userName')]) {
                        def remote = [:]
                        remote.name = 'test'
                        remote.host = '18.116.238.113'
                        remote.user = userName
                        remote.identityFile = keyFile
                        remote.allowAnyHosts = true
                        writeFile file: 'deployment.sh', text: 'if [ true ]; then\n	echo \'trueee\'\nelse\n	echo \'falseee\'\nfi', sudo: true
                        sshScript remote: remote, script: "deployment.sh"
                    }    
                }
			}
        }
    
    }
}
