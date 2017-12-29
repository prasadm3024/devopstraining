 pipeline
{ 
    agent {
        label "windows"
    }
        tools
        {
        maven "Maven"
        jdk "JDK"
        }
        
    stages { 
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                    doGenerateSubmoduleConfigurations: false, extensions: [], gitTool: 'Git installations Windows', submoduleCfg: [], 
                    userRemoteConfigs: [[credentialsId: '0ab2ce6b-c203-4019-bc26-033fe0b6bfd2', url: 'https://github.com/prasadm3024/devopstraining.git']]])
                  }
                         }
        stage('Build') { 
            steps { 
               echo 'This is a minimal pipeline.' 
                  }
                        }
    stage ('Build2') {

            steps {

                bat "cd payslip & mvn clean install"

                    }
    
            post {

                success {

                    junit "payslip/target/surefire-reports/*.xml"

                        }

                }
                      }
}
}

