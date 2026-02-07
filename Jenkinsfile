pipeline{
    agent any

    tools {
        dotnetsdk 'dotnet8'
    }

    stages{
        stage("Restore dependencies"){
            steps{
                sh 'dotnet restore'
            }
            post{
                always{
                    echo "Step executed successfully"
                }
            }
        }
        stage("Build solution"){
            steps{
                sh 'dotnet build'
            }
        }
        stage("Run tests"){
            steps{
                sh 'dotnet test'
            }
        }
    }

    post{
        always{
            echo "Workflow completed successfully"
        }
    }
}
