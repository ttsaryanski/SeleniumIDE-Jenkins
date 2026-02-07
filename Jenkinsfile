pipeline{
    agent any
    stages{
        stage("Install dependencies"){
            steps{
                bat 'dotnet restore'
            }
            post{
                success{
                    echo "========Instalation executed successfully========"
                }
                failure{
                    echo "========Instalation execution failed========"
                }
            }
        }
        stage("Build"){
            steps{
                bat 'dotnet build --no-restore'
            }
            post{
                success{
                    echo "========Build executed successfully========"
                }
                failure{
                    echo "========Build execution failed========"
                }
            }
        }
         stage("Test"){
            steps{
                bat 'dotnet test --no-build --no-restore'
            }
            post{
                success{
                    echo "========Test executed successfully========"
                }
                failure{
                    echo "========Test execution failed========"
                }
            }
        }
    }
    post{
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}