pipeline{
    agent{
        label "node"
    }
    stages{
        stage("Restore Dependencies"){
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat 'dotnet build'
            }
        }
        stage("Build the app"){
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat 'dotnet build --no-restore'
            }
        }
        stage("Run the tests"){
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps{
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}