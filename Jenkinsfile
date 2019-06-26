node 
{
   def mvnHome
   stage('scm checkout') { 
      
      git 'https://github.com/devopsmastek/java_app_cloud.git'
                
      
   }
   stage('Build') {
     def MVN_HOME = tool name: 'MAVEN', type: 'maven'
     def MVNCMD = "${MVN_HOME}/bin/mvn"
      sh "${MVNCMD} clean package"
      }
   
   stage ('deploy')
          {
  
    sh "cp /var/lib/jenkins/workspace/Java_app/target/*.war /var/lib/tomcat8/webapps"
      
              
          
         }
}
