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
                        sshCommand remote: remote, command: "ls -l"
                        sshCommand remote: remote, command: "pwd"
                    }    
                }
			}
        }
    
    }
}
//             writeFile file: 'abc.sh', text: 'ls'
//             sshCommand remote: remote, command: 'for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done'
//             sshPut remote: remote, from: 'abc.sh', into: '.'
//             sshGet remote: remote, from: 'abc.sh', into: 'bac.sh', override: true
//             sshScript remote: remote, script: 'abc.sh'
//             sshRemove remote: remote, path: 'abc.sh'
        
