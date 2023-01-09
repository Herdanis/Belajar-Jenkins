pipeline{
    agent any
    tools{
        go "go 1.19"
    }
	parameters{
		booleanParam(name:"DEPLOY",defaultValue:false,description:"Need to deploy")
	}
    stages{
        stage("prepare"){
			environment{
				APP = credentials("qwe")
			}
            steps{
                echo("start job : ${env.JOB_NAME}")
                echo("branch Name : ${env.JOB_BRANCH}")
				sh('echo "app_password : $APP" > "rahaisa.txt"')
            }
        }
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
			input{
				message "Can we Deploy"
				ok "Deploy"
			}
			steps{
				withCredentials([userpassword(
					credentialsId: "gitlab",
					usernameVariable: "name",
					passwordVariable: "secret"
				)]){
					script{
						def data = [
							"firstname" : "tes",
							"lastname" : "qwe"
						]
						writeJSON(file: "data.json", json:data)
					}
					sh('echo "user : $name pass : $secret"')
					sh("./main")
				}
            }
        }
		stage("release"){
			when{
				expression{
					return params.DEPLOY
				}
			}
			steps{
				echo("deployed")
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