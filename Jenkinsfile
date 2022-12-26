pipeline{
    agent any
    tools{
        go "1.19.0"
    }
    stages{
        stage("build"){
            steps{
                sh "go build -o main"
            }
        }
        stage("test"){
            steps{
                echo("go test")
            }
        }
        stage("deploy"){
            steps{
                sh "./main"
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
