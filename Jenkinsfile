pipeline{
    agent any
       
    stages{
        stage("git-checkout"){
            steps{
                    echo 'Hello World'
              git branch: 'main', url: 'https://github.com/rajtirole/Jenkinsfile'
            }
        }
        stage("A"){
            steps{
                echo "========executing A========"
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
