pipeline { 
    agent any  
    stages { 
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                    doGenerateSubmoduleConfigurations: false, extensions: [], gitTool: 'Git installations Windows', submoduleCfg: [], 
                    userRemoteConfigs: [[credentialsId: '0bde1bacd4d52d060d30573b01ce7c5d746e38b0', url: 'https://github.com/prasadm3024/devopstraining.git']]])
            }
        }
        stage('Build') { 
            steps { 
               echo 'This is a minimal pipeline.' 
            }
        }
    stage ('Build2') {

            steps {

                bat 'cd payslip & mvn clean install' 

            }

            post {

                success {

                    junit 'payslip/target/surefire-reports/**/*.xml' 

                }

            }
    }
}

