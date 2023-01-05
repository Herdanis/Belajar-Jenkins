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
            steps{
                script{
                    for (int i = 0; i < 10; i++) {
                        echo("Script ${i}")
                    }
                }
                echo("go test")
                echo("go yo")
            }
        }
        stage("deploy"){
            steps{
                script{
                    def data = [
                        "firstname" : "tes",
                        "lastname" : "qwe"
                    ]
                    writeJSON(file: "data.json", json:data)
                }
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
