CODE_CHANGES = getGitChanges()
pipeline{
    agent any

    stages {
        stage("build") {
            when{
                expression {
                    BRANCH_NAME == 'dev' && CODE_CHANGES = true
                }
            }
            steps {
                echo 'Hello'
            }
        }    
        stage("Test") {
            when {
                expression {
                    env.BRANCH_NAME='dev' || env.BRANCH_NAME='master'
                }
            }
            steps {
                echo 'World'            
            }
        }
        stage("Deploy"){
            steps{
                echo 'Deployed'
            }
        }
    }
    post {
        always{

        }
    }
}
