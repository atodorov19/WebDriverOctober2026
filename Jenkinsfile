pipeline{
    agent any
/// Adding the stages for the pipeline
    stages{
        stage("Checkout the code"){
            steps{
                bat 'dotnet restore'
            }
        }
        stage("Build the project"){
            steps{
                bat 'dotnet build -no-restore'
            }            
        }
        stage("Run different project tests"){
            parallel{
                stage("Project1 Tests"){
                    steps{
                        bat 'dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal'
                    }
                }
                stage("Project2 Tests"){
                    steps{
                        bat 'dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal'
                    }
                }
                stage("Project3 Tests"){
                    steps{
                        bat 'dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal'
                    }
                }
                }
            }
        }
    }
