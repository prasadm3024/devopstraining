node
{ 
 def maven = tool 'Maven'
 def jdk = tool 'JDK8'
 stage('Checkout') {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                    doGenerateSubmoduleConfigurations: false, extensions: [], gitTool: 'Git installations Windows', submoduleCfg: [], 
                    userRemoteConfigs: [[credentialsId: '0ab2ce6b-c203-4019-bc26-033fe0b6bfd2', url: 'https://github.com/prasadm3024/devopstraining.git']]])
 }
                       def pom = readMavenPom file: 'pom.xml'
  def version = pom.version.replace("-SNAPSHOT", ".${currentBuild.number}")
 stage('BUILD'){
  "${mvnHome}/bin/mvn -DreleaseVersion=${version} -DdevelopmentVersion=${pom.version} -DpushChanges=false -DlocalCheckout=true -DpreparationGoals=initialize release:prepare release:perform -B"
 }
 stage('Build')         {
               echo 'This is a minimal pipeline.' 
 }
    stage ('Build2') {
              sh  "mvn clean install"
    }
    // stage ('test'){
         //           junit "payslip/target/surefire-reports/*.xml"
         //               }
          }
 
