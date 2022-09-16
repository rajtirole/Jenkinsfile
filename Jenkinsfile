pipeline{
    agent any
        environment{
        PATH_JENKINS="/root/lokii:$PATH"
       }
    stages{
        stage("git-checkout"){
            steps{
                    echo 'Hello Worldssdsad'
              git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
            }
        }
        stage("A"){
            steps{
                echo "========executing A========"
                 sh "apt update"
                sh "apt install maven"
                 sh "mv clean pakage"
            }
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
