pipeline{
    agent any
    tools{
        go "go 1.19"
    }
    stages{
        stage("build"){
            steps{
                sh("go build -o main")
            }
        }
        stage("test"){
            script{
                for (int i = 0; i <10; i) {
                    echo("Script ${i}")
                }
            }
            steps{
                echo("go test")
                echo("go yo")
            }
        }
        stage("deploy"){
            steps{
                sh("./main")
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
