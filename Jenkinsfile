pipeline{
    agent any
    stages{
        stage("build"){
            steps{
                echo("build")
            }
        }
        stage("test"){
            steps{
                echo("test")
            }
        }
        stage("deploy"){
            steps{
                echo("deploy")
            }
        }
    }
    post{
        always{
            echo "Done"
        }
        success{
            echo "Sukses"
        }
        failure{
            echo "Fail"
        }
        cleanup{
            echo "Cleanup"
        }
    }
}
