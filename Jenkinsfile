node 
{
   def mvnHome
   stage('scm checkout') { 
      
      git 'https://github.com/devopsmastek/Java_app.git'
                
      
   }
   stage('Build') {
     def MVN_HOME = tool name: 'MAVEN', type: 'maven'
     def MVNCMD = "${MVN_HOME}/bin/mvn"
      sh "${MVNCMD} clean package"
      }
   
   stage ('deploy)
          {
   sshagent(['tomcat-ssh']) {
    sh 'scp -o StrickHostKeyChecking=no target/*.war ubuntu@13.232.244.198:/var/lib/tomcat8/webapps/'
              }
          
         }
}
