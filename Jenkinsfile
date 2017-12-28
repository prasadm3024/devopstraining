
pipeline { 
    agent any  
    stages { 
        stage('Git'){
                 steps {
            script {
                GIT_COMMIT = bat (
                    script: 'git rev-parse HEAD',
                    returnStdout: true
                ).trim()

                GIT_URL = bat (
                    script: 'git config --get remote.origin.url',
                    returnStdout: true
                ).trim()
            }
        }  
     }         
        stage('Build') { 
            steps { 
               echo 'This is a minimal pipeline.' 
            }
        }
    }
}
